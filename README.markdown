# tnythumb

## Story time!

So I was looking at [The Earth at Night](http://visibleearth.nasa.gov/view_rec.php?id=1438) on NASA's website, and I
downloaded the 30000x15000 GIF to my desktop. Suddenly, my computer
started using a lot of memory. As it turns out, nautilus had decided
that the image, being only 6.0MiB, ought to be thumbnailed, and proceeded
to decompress the image.

Unfortunately, that many pixels take about 1.7GiB. ImageMagick and the
GIMP did a little better by using the disk as a temporary space instead,
but the fact remains that creating the thumbnail was slow and painful.

There ought to be a more efficient way, uncompressing only the currently
needed pixels. If you want to create a 100x100 thumbnail from the image
at hand, you are scaling down by a factor of 150 in the vertical axis,
so you should never need to keep more than (some multiple of) that many
rows on hand at a time.

## Planning

In the long run, I am hoping to support PNG, JPEG (both JFIF and TIFF)
and possibly GIF.

## References

* [JPEG](https://secure.wikimedia.org/wikipedia/en/wiki/JPEG) on Wikipedia
* [libpng](http://www.libpng.org/pub/png/libpng.html)
