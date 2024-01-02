#### Lecture 5 - region processing / convolution
vid 1
- Region processing = functions involving more than one source pixel
- Detecting vertical = $|I(x,y) - I(x,y+1)|$
- Detecting horizontal = $|I(x,y)-I(x,y+1)|$
- combining with city block (just add), euclidean, OR operation
vid 2
- convolution, where $W$ is filter kernel
![](https://i.imgur.com/odO4tX1.png)- ==convolution flips the kerne==l, while correlation doesnt, most image processing software will do correlation but call it convolution - just do $w0*i0$ if in doubt 
- normalisation exists to not get return value which is too large - either perform on result of convolution for a pixel or normalise the mask
- convolution is associative - therefore you can separate kernels to perform less multiplications/additions for efficiency gane
vid 3 - ==convolution applications==
- averaging kernel - box filter. 3x3 all containing $\frac{1}{9}$
- sharpening kernel to enhance discontinuities but amplify noise:
![|100](https://i.imgur.com/P20d2jA.png)
- ==laplacian==: same as sharpening ==but with 4 in centre== - only picks up edges since uniform areas will cancel themselves out
- ==noise is a deviation of a value from its expected value==
- salt and pepper = $x \rightarrow \{\text{max},\text{min}\}$
- noise reduction via smoothing (with/without box filter)
- $\sum(x) + \sum(n) \approx \sum(x)$ since noise is random and has a mean of 0
- adaptive smoothing (taking a smoothed value if it doesnt differ from original value too much)
![|200](https://i.imgur.com/SlTPGgX.png)
- 2d gaussian smoothing using filter
![|400](https://i.imgur.com/xwxOV77.png)
- ==median filter is a type of rank filter==- just takes median from values in each kernel - extremely noisy pixels have less of an effect on kernels by using a median
- other rank filters include: max, min

#### Lecture 6 - Edge detection cont.
vid 1
- ==edge = extended, significant, local change in image intensity==
- calculating gradient of a pixel (in horizontal/vertical direction) - do (next pixel value - current pixel value) to get current pixel gradient
- use gradient in x and y to calculate magnitude/direction of gradient vector
![|200](https://i.imgur.com/W8LEEEZ.png)
- edge normal = pixel gradient vector is perpendicular to edge its on
![|200](https://i.imgur.com/tfiBrjJ.png)
- roberts cross edge detector (not used very much)
![|400](https://i.imgur.com/4IxAwAX.png)
- prewitt operator (left for horizontal, right for vertical)
![|300](https://i.imgur.com/NuQkDBS.png)
- ==prewitt== filter reduces noise as it can be separated into two kernels, one of which is an averaging filter that smooths out rows, and the other is an edge detector
![|300](https://i.imgur.com/5mY6EuY.png)
vid 2
- ==sobel== filter - similar to prewitt, except 2 in the middle instead of 1, giving a weighted avg. rather than regular avg
![|300](https://i.imgur.com/5AIaiuj.png)
- ==canny edge detection main requirements==:
	1. accurately find as many edges in image without false detection
	2. accurately localise edge points on the centre of the edge (works with 3x3, not 2x2)
	3. given edge should only be marked once
- ==canny edge steps==:
	1. pick kernel and apply gaussian smoothing
	2. apply edge detection, and calculate gradient magnitude/direction for each pixel (since these are on edges, these are edge normals)
	3. classify edge normals (gradient vectors of edge pixels) as horizontal, vertical, 45 or -45, into image $\theta$
	4. non maxima suppression - contain thin edges in image by picking pixels from classified image $\theta$ where 2+ neighbouring pixels have same dir but higher mag
	5. use two thresholds $T_L$/$T_H$ on thin edges:
		- below $T_L$ = not an edge
		- between $T_L$ and $T_H$ = weak
		- above $T_H$ = strong
	6. create binary images of strong edges and weak edges (remove strong edges from the weak edges image, since you'd threshold above $T_L$)
	7. final binary image = strong image pixels + set any corresponding neighbour pixels which r set in weak image (connectivity analysis)
- $T_H$ should be 2x/3x higher than $T_L$
vid 3
- laplacian performs second derivative on image - a single kernel can be used, but noise gets highlighted
- ==laplacian of gaussian = gaussian blur -> convolution w/ laplacian==
- ==marr-hildeth = laplacian of gaussian with signed arithmetic, then mark edge pixels if signs differ for any opposing pixels in 3x3? (zero-crossing pixels)==
- difference of gaussian = gaussian blur with 2 sigmas, then subtracting one from the other
- template matching = finding smaller image within bigger image
- template matching is done with cross correlation (convolution equation but flipped, so actually using + symbols)
- normalise the result by dividing by region sum to avoid white area giving largest vals
- in short template matching trash - use feature detection