# $\delta$ not $\pi$
Investigations into whether $\pi/4$ is actually a more natural constant that $\pi$ or $\tau$.


## Where this conversation started

Several years ago the idea of using a constant $\tau$, equal to twice the value of $\pi$, instead of $\pi$, floated around the internet, largely driven by the formula $C=2 \pi r$, claiming that this would make things easier for students, particularly when working with trigonometry. See [here](https://youtu.be/ZPv1UV0rD8U?si=AuIwq0wTOF8zGKLr). It was correctly derided as a terrible idea.

Recently, I watched [this video](https://youtu.be/tD5NrevFtbU?si=-HuQcc4XvUntE6TB) about code performance. Mostly, the video is irrelevant to the field of mathematics, other than triggering a thought process in my own mind. In the video, several shapes area created as a generic object with a type attribute(`SQUARE`, `RECTANGLE`, `TRIANGLE`, and `CIRCLE`), each shape must have a type and a `width`, but an optional `height` attribute was also available. What was of mathematical interest to me was that the area of a `SQUARE` was implemented as 

$$ area = width \cdot width $$ 

as one would expect. Similarly for the areas of `TRIANGLE` and `RECTANGLE`. However, the area of a circle was implemented as 

$$
area = \pi \cdot width \cdot width
$$. 

It was this later implementation that caught my attention. In all the shapes except `CIRCLE`, the width represented the maximum distance between some set of points on the shape, but for `CIRLCE`, `width` for some reason did not represent the distance between two points on the shape, let alone some kind of maximum. Using the same attribute to represent two totally different concepts is considered a poor practice in programming, so in my own explorations of the subject, I reimplemented the area of circle based on the diameter, which yielded 

$$
area = \pi \cdot \frac{width}{2} \cdot \frac{width}{2}
$$ 
or 
$$
area = \frac{\pi}{4} \cdot width \cdot width
$$. 

For the remainder of this discussion, let's call the value $\frac{\pi}{4}$ as $\delta$. ($\pi$ is the $16^{th}$ letter of the Greek alphabet and $\delta$ is the fourth). Having exhausted my own exploration of clean code vs performance, my mind returned to this alternate formula for the area of the circle. It was at this point that I remembered the $\tau$ vs $\pi$ argument and wondered if perhaps $\delta$ had some value in a similar argument. The key insight for me, was that $\delta$ was smaller than 1 (about 0.785), and therefore could be interpreted as a percentage.

# First Arguments for $\delta$

So why might $\delta$ have some value in understanding the world that $\pi$(and consequently $\tau$) does not? Let's start with basic definitions. 

$\pi$ is defined as the ratio of the circumference of a circle to its diameter.

What about $\delta$? In a similar vein, we can describe $\delta$ as the ratio of the area of a circle to its circumscribing square.

While neither of these areas truly please me (how are we getting these true measurements of the circumference/area of circles?), I will argue that the second definition actually makes the math make more sense.

When we look at the traditional formula for the area of a circle, $A=\pi\cdot r^2$, we are left with the magic constant $\pi$ as something that we just have to memorize. On the other hand, the formula $A=\delta\cdot width^2$ actually makes sense because delta is the fraction of the area of the circle inside the square with sides equal to the diameter of the circle. You could argue this a tautology so let's investigate further. What about perimeter/circumference?

The circumference of a circle is traditionally given by 

$$
C=\pi\cdot width
$$

where we use $width$ to represent the diameter of the circle. Using the conversion $\pi=4\delta$, this becomes 

$$
C=4\delta\cdot width
$$.

So what? Let's rearrange that further and look deeper. 

$$
C=\delta\cdot 4\cdot width
$$. 

Of particular interest is the term $4\cdot width$. This is the perimeter for the circumscribing square! Again, we can understand the similar concept for a circle in terms of a fraction of the formula for the circumscribing square. And not only is the relationship parallel, but it is in fact the same relationship! A circle is a fixed fraction of its circumscribing square. It becomes clear that a powerful way to conceptualize a circle is as a fraction of its circumscribing square.

To summarize, given a circle of diameter $w$ and a square with sides of length $w$, we have the following relationships.

### Definitional Values

$$
\delta = \frac{\pi}{4} \approx 0.7854
$$


### Area

$$
A_{square} = w^2 \\
A_{circle} = \delta \cdot w^2 = \delta \cdot A_{square}
$$


### Perimeter

And if we acknowledge that circumference is just a special case of perimeter:

$$
P_{square} = 4 w \\

P_{circle} = \delta \cdot 4 w = \delta \cdot P_{square}
$$
