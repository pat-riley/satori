# Fractals & Recursion

The term fractal (from the Latin fractus, meaning “broken”) was coined by the mathematician Benoit Mandelbrot in 1975. In his seminal work “The Fractal Geometry of Nature,” he defines a fractal as “a rough or fragmented geometric shape that can be split into parts, each of which is (at least approximately) a reduced-size copy of the whole.”

Looking closely at a given section of the tree, we find that the shape of this branch resembles the tree itself. This is known as self-similarity; as Mandelbrot stated, each part is a “reduced-size copy of the whole.”

## Recursion 

Let’s begin our discussion of recursion by examining the first appearance of fractals in modern mathematics. In 1883, German mathematician George Cantor developed simple rules to generate an infinite set:

##### Recursion Example
```
void someFunction() {
	someFunction();
}	
```

In fact, this is not only allowed, but it’s quite common (and essential to how we will implement the Cantor set). Functions that call themselves are recursive and good for solving certain problems. For example, certain mathematical calculations are implemented recursively; the most common example is factorial.

##### Factorial Example
```
int factorial(int n) {
	int f = 1;
	for (int i = 0; i < n; i++) {
		f = f * (i+1);
	}
return f;
}
```

##### Recursive Circles
```
void drawCircle(int x, int y, float radius) {
  ellipse(x, y, radius, radius);
  if(radius > 2) {
    radius *= 0.75f;
    drawCircle(x, y, radius);
  }
}
```













