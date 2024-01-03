[[COMP37111]]

- curve subdivision is useful for adding finer details to already existing curves, while avoiding the complexity of using a higher degree curve - subdividing a bezier curve leaves you with 2 new bezier curves, which each have the same number of control points as their parents (you effectively double the number of control points)
- this is due to the fact that you're more or less splitting the curve at some point $t$, thus the type of curve you're dealing with wouldn't lose any degree
![300](https://i.imgur.com/3KmWsv1.png)

# de casteljau subdivision (cubic bezier)
1. start with 4 control points - find the midpoint between the all control points apart from the 2 initial anchor points, such that you have 3 midpoints (==you dont have to do midpoints either, if you dont want 2 halves of the curve==)
2. repeat this division until the curve is flat enough (?)
3. you will be left with new control points for the subdivided curves

needs working on
