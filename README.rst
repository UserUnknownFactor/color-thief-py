Color Thief
===========

A Python module for grabbing the color palette from an image.

Installation
------------

::

    $ pip install colorthief

Usage
-----

.. code:: python

    from colorthief import ColorThief

    color_thief = ColorThief('/path/to/imagefile')
    # get the dominant color
    dominant_color = color_thief.get_color(quality=1)
    # build a color palette
    palette = color_thief.get_palette(color_count=6)

API
---

.. code:: python

    class ColorThief(object):
        def __init__(self, input_stream, default_color=None):
            """Create one color thief for one image.

            :param input_stream: A filename (string) or a file object or Image or raw RGBA pixel list.
            :param default_color: color to use if no matches found: (0xFF,0xFF,0xFF), None, etc.
            """
            pass

        def get_color(self, quality=1, no_white=True, no_black=True, dist=False):
            """Get the dominant color.

            :param quality: quality settings, 1 is the highest quality, the bigger
                            the number, the faster a color will be returned but
                            the greater the likelihood that it will not be the
                            visually most dominant color
            :param no_white: ignore white pixels if True
            :param no_black: ignore black pixels if True
            :param dist: return pixel with its frequency if True
            :return tuple: (r, g, b)
            """
            pass

        def get_palette(self, color_count=10, quality=1, no_white=True, no_black=True, dist=False):
            """Build a color palette.  We are using the median cut algorithm to
            cluster similar colors.

            :param color_count: the size of the palette, max number of colors
            :param quality: quality settings, 1 is the highest quality, the bigger
                            the number, the faster the palette generation, but the
                            greater the likelihood that colors will be missed.
            :param no_white: ignore white pixels if True
            :param no_black: ignore black pixels if True
            :param dist: return pixels with their distribution if True
            :return list: a list of tuples in the (r, g, b) form
            """
            pass

Thanks
------

Thanks to Lokesh Dhakar for his `original work
<https://github.com/lokesh/color-thief/>`_.

Improvements
------

If you feel anything wrong, feedbacks or pull requests are welcome.
