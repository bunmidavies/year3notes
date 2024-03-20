[[COMP35112]]

```C
MPI_Send(void* data, int cnt, MPI_Datatype t, int dst, int tag, MPI_Comm com);
MPI_Recv(void* data, int cnt, MPI_Datatype t, int src, int tag, MPI_Comm com, MPI_Status* st);
```

- `data`: pointer to the data to send/receive
- `cnt`: number of items to send/receive
- `t`: the type of data, e.g. `MPI_INT`, `MPI_DOUBLE` etc.
- `dst`/`src`: rank of the receiving/sending process - you only need to specify one or the other for either method (since your own rank will either be the src or dst)
- `tag`: integer tag, to receive any tag use `MPI_ANY_TAG`
- `com`: the communicator (used for specific process groups) - `MPI_COMM_WORLD` is the 'world' group
- `st`: status information

# bouncing counter example
- a singular payload/value 'bounces' between a number of process, who each increment the payload value then send the new incremented value to another random process, which does the same thing, until a certain value is reached
```C
...
// only ONE process will initialise the counter
if (my_rank == 0)
{
	int payload = 0;
	int target_rank = 0;
	while (target_rank == my_rank)
		target_rank = rand()%world_size;

	printf("[%d] sent int payload %d to %d\n", my_rank, payload, target_rank);
	MPI_Send(&payload, 1, MPI_INT, target_rank, 0, MPI_COMM_WORLD);
}

// ALL processes now execute this code
while (1)
{
	int payload;
	// receive the payload from any process
	MPI_Recv(&payload, 1, MPI_INT, MPI_ANY_SOURCE, 0, MPI_COMM_WORLD, MPI_STATUS_IGNORE);

	if (payload == -1) {
		printf("[%d] received stop signal, exiting\n", my_rank);
		break;
	}

	// if payload has been incremented a limited number of times
	if (payload == BOUNCE_LIMIT) // 20 in example
	{
		int stop_payload = -1;
		printf("broadcasting stop signal\n");
		// iterate through all processes
		for (int i = 0; i < world_size; i++)
		{
			// make sure youre not messaging yourself
			if (i != my_rank)
				MPI_Send(&stop_payload, 1, MPI_INT, i, 0, MPI_COMM_WORLD);
		}
		break;
	}

	payload++;
	int target_rank = my_rank;
	// pick new target to bounce to
	while (target_rank == my_rank) target_rank = rand()%world_size;

	printf("[%d] received payload %d, sending %d to %d\n", my_rank, payload-1, payload, target_rank);

	MPI_Send(&payload, 1, MPI_INT, target_rank, 0, MPI_COMM_WORLD);
}

MPI_Finalize();

```