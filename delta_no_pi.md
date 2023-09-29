# $\delta$ not $\pi$
Investigations into whether $\pi/4$ is actually a more natural constant that $\pi$ or $\tau$.


## Where this conversation started

Several years ago the idea of using a constant $\tau$, equal to twice the value of $\pi$, instead of $\pi$, floated around the internet, largely driven by the formula $C=2 \pi r$, claiming that this would make things easier for students, particularly when working with trigonometry. See [here](https://youtu.be/ZPv1UV0rD8U?si=AuIwq0wTOF8zGKLr). It was correctly derided as a terrible idea.

Recently, I watched [this video](https://youtu.be/tD5NrevFtbU?si=-HuQcc4XvUntE6TB) about code performance. Mostly, the video is irrelevant to the field of mathematics, other than triggering a thought process in my own mind. In the video, several shapes area created as a generic object with a type attribute(`SQUARE`, `RECTANGLE`, `TRIANGLE`, and `CIRCLE`), each shape must have a type and a `width`, but an optional `height` attribute was also available. What was of mathematical interest to me was that the area of a `SQUARE` was implemented as 

$$ area = width \cdot width $$ 

as one would expect. Similarly for the areas of `TRIANGLE` and `RECTANGLE`. However, the area of a circle was implemented as 

$$ area = \pi \cdot width \cdot width $$

It was this later implementation that caught my attention. In all the shapes except `CIRCLE`, the width represented the maximum distance between some pair of points on the shape, but for `CIRLCE`, `width` for some reason did not represent the distance between two points on the shape itself. Using the same attribute to represent two totally different concepts is considered a poor practice in programming, so in my own explorations of the subject, I reimplemented the area of circle based on the diameter, which yielded 

$$ area = \pi \cdot \frac{width}{2} \cdot \frac{width}{2} $$ 

or 

$$ area = \frac{\pi}{4} \cdot width \cdot width $$ 

For the remainder of this discussion, let's use $\delta$ to denote the value $\frac{\pi}{4}$ ($\pi$ is the $16^{th}$ letter of the Greek alphabet and $\delta$ is the $4^{th}$). Having exhausted my own exploration of clean code vs performance, my mind returned to this alternate formula for the area of the circle. It was at this point that I remembered the $\tau$ vs $\pi$ argument and wondered if perhaps $\delta$ had some value in a similar argument. The key insight for me, was that $\delta$ was smaller than 1 (about 0.785), and therefore could be interpreted as a percentage.

# First Arguments for $\delta$

So why might $\delta$ have some value in understanding the world that $\pi$(and consequently $\tau$) does not? Let's start with basic definitions.

A circle is the set of all points a fixed distance from a central point. In other words, a circle is defined by its center and radius.

$\pi$ is the ratio of the circumference of a circle to its diameter. And $\tau$ is the ratio of the circumference of a circle to its radius.

I have a couple of issues with these definitions.

1. They require us to measure the circumference of a circle, which we know is impossible empirically, because we know both values are irrational. The definition of $\tau$ is particularly problematic in this regard because given a circle we have to measure both the circumference and the radius, neither of which are easy to measure.
2. Both definitions are in terms of the circle. While this may seem mathematically pure, it leaves us with values that provide no insight into the nature of a circle other than that there is a "circle constant." In this regard, we can even concede that $\tau$ is the more "pure" of definitions because it goes back a defining property of the circle, its radius.
3. Both of these definitions define the "circle constant" in terms of lengths. But a circle is a two dimensional shape and it feels that a definitional constant for a two dimensional shape should have two dimensional meaning.

Of these issues, I don't have any good answers for trying to measure a circle. At some point a shape does have to be measured by its characteristics and circles are just hard in this regard. See the existence of these "circle constants". If you've read this and said, but area is even harder to measure, I agree, but keep reading. Obviously, we've already seen that $\delta$ satisfies the second issue by teaching us how circles are related to their circumscribing squares, which also satisfies the third point. But if you stick with me, we'll see that there is something truly innate about $\delta$ that makes it universal while $\pi$ and $\tau$ are not.

What about $\delta$? Based on what we've discussed thus far, $\delta$ is the ratio of the area of a circle to the area of its circumscribing square.

We can summarize that relationship as

$$ A_{circle}=\delta \cdot A_{square} $$

when the square has the same width (i.e. diameter) of the circle.

This gives us a definition of $\delta$ that

1. Tells us about a circle in terms of the shape we measure all other two dimensional shapes by, the square. It makes us more knowlegable about circles and their relationship to the rest of the two dimensional world.
2. Tells us about a circle in terms of its two dimensionalness, its area.

This is all well and good, but quite honestly makes the first problem of measurement even worse. So is there an easier way to measure delta?

$\tau$ and $\delta$ solve this problem by falling back to measurements of length, so let's see what happens with $\delta$ when we explore perimeter(i.e. circumference)?

The circumference of a circle is traditionally given by 

$$ C=\pi\cdot width $$

where we use $width$ to represent the diameter of the circle. Using the conversion $\pi=4\delta$, this becomes 

$$ C=4\delta\cdot width $$

So what? Let's rearrange that further and look deeper. 

$$ C=\delta\cdot (4\cdot width) $$ 

Of particular interest is the quantitity $4\cdot width$. This is the perimeter for the circumscribing square! Again, we can understand the similar concept for a circle in terms of a fraction of the formula for the circumscribing square. And not only is the relationship parallel, but it is in fact the same relationship! A circle is a fixed fraction of its circumscribing square. It becomes clear that a powerful way to conceptualize a circle is as a fraction of its circumscribing square.

To summarize, given a circle of diameter $w$ and a square with sides of length $w$, we have the following relationships.

### Definitional Values

$$ \delta = \frac{\pi}{4} = \frac{\tau}{8} \approx 0.7854 $$


### Area

$$
\begin{align}
A_{square} = w^2 \\
A_{circle} = \delta \cdot w^2 = \delta \cdot A_{square}
\end{align}
$$


### Perimeter

And if we acknowledge that circumference is just a special case of perimeter:

$$
\begin{align}
P_{square} = 4 w \\
P_{circle} = \delta \cdot 4 w = \delta \cdot P_{square}
\end{align}
$$

In particular, the perimeter of a circle with diameter 1 is just $4\delta$.

## We're Going 3D

Let's take a moment to see how $\delta$ impacts our values for spheres.

For the remainder of this section, we will work with a circle of radius $r$ and diameter $w=2r$ as well as cube of side length $w$. Additionally, recall the relationship $\pi=4\delta$.

The volume of the cube follows the traditional formula $V_{cube}=w^3$.

The volume of the sphere is

$$ V_{sphere} = \frac{4}{3}\pi r^3 = \frac{2\delta}{3}w^3 = \frac{2\delta}{3} V_{cube} $$

Let's see what happens with surface area before we hit much discussion.

The surface area of a square is given by $S_{square}=6w^2$.

For a sphere we have 

$$ S_{sphere}=4\pi r^2 = 4\delta w^2 $$
Now, to jump a bit to the conclusion, the volume relationship suggests that in three dimensions the "sphere constant" should be $\frac{2\delta}{3}$. A little algebra gives us

$$ S_{sphere} = \frac{2\delta}{3} 6w^2 = \frac{2\delta}{3}S_{cube} $$

In other words, $\delta$ defines a constant relationship not only between circles and equally wide squares but spheres and equally sized cubes.

In fact, we can find a similar relationship for any higher dimensional n-sphere and n-cube of equal widths.

$$ V_{n-sphere}=\frac{\delta^\frac{n}{2}}{\Gamma(\frac{n}{2} +1)} V_{n-cube} $$

and then

$$ S_{n-sphere}=\frac{\delta^\frac{n}{2}}{\Gamma(\frac{n}{2} +1)} S_{n-cube} $$

Where $\Gamma$ is the gamma function, which can be thought of as an extension of factorial to all positive real numbers. Of particular note is that the use of delta actually makes the formulas for n-spheres cleaner, removing several seemingly arbitrary factors that appear when using $\pi$.

Additionally we see that the use of $\delta$ in no way obscures any other formulas that involve $\pi$:

* Area of an ellipse with width $a$ and height $b$: $A=\delta ab$
