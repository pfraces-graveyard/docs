# fit in the given area

    $ convert hokusai.jpg.original  -resize 1920x1080 hokusai.jpg

# fit out the given area

    $ convert hokusai.jpg.original  -resize 1920x1080^ hokusai.jpg

# match the given area

## does not respect aspect ratio

    $ convert hokusai.jpg.original  -resize 1920x1080\! hokusai.jpg

## respect aspect ratio and crop

    $ convert hokusai.jpg.original  -resize 1920x1080^ \
      -gravity Center -extent 1920x1080 hokusai.jpg

### gravity types

Choices include:

*   NorthWest
*   North
*   NorthEast
*   West
*   Center
*   East
*   SouthWest
*   South
*   SouthEast

Use `-list gravity` to get a complete list of `-gravity` settings available in
your **ImageMagick** installation
