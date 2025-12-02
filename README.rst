This update is a small kludge due to what appears to be something in Python or 
iPython that breaks this package - Pyhton appears to no longer like packages
that start with a capital letter. Note the small syntax changes - everything
needs to be geohash.gh.<function> instead of geohash.<function> . I could
probably fix this to be a little nicer, but I really just need to get my 
work done.

Note also the changes on decode... use decode_exactly.

=======
Geohash
=======

Geohash is a Python module that provides functions for decoding and
encoding Geohashes_ to and from latitude and longitude coordinates.

Example::

  >>> import geohash
  >>> print(f'Geohash for 42.6, -5.6: {geohash.gh.encode(42.6, -5.6)}')
  Geohash for 42.6, -5.6: ezs42e44yx96

You can specify an arbitrary precision when encoding. The precision
determines the number of characters in the Geohash::

  >>> print(f'Geohash for 42.6, -5.6: {geohash.gh.encode(42.6, -5.6, precision = 5)}')
  Geohash for 42.6, -5.6: ezs42

Decoding a Geohash returns a (latitude, longitude) tuple::

  >>> print(f"Coordinate for Geohash ezs42: {geohash.gh.decode('ezs42')}")
  Coordinate for Geohash ezs42: ('(1, 42.60498046875)', '(1, -5.60302734375)')

The Geohash module also provides exact decoding with error margin
results. The decode_exactly function returns a tuple of four float
values; latitude, longitude, latitude error margin, longitude error
margin::

  >>> print(f"Exact coordinate for Geohash ezs42:\n{geohash.gh.decode_exactly('ezs42')}")
  Exact coordinate for Geohash ezs42:
  (42.60498046875, -5.60302734375, 0.02197265625, 0.02197265625)

The last two values are the plus/minus error margin of the latitude
and longitude respectively. In this particular case the error margins
happen to be the same for both the latitude and the longitude, but
this is just a co-incidence due to the precision of the Geohash and
thus the number of bits used for the latitude and longitude encoding,
respectively.

Download
========

Geohash is available for download from github_ and from the `Python Package Index`_.

License
=======

Copyright (C) 2008 Leonard Norrgard <leonard.norrgard@gmail.com>
Copyright (C) 2015 Leonard Norrgard <leonard.norrgard@gmail.com>

Geohash is free software: you can redistribute it and/or modify it
under the terms of the GNU Affero General Public License as published
by the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

Geohash is distributed in the hope that it will be useful, but WITHOUT
ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or
FITNESS FOR A PARTICULAR PURPOSE.  See the GNU Affero General Public
License for more details.

You should have received a copy of the GNU Affero General Public
License along with Geohash.  If not, see
<http://www.gnu.org/licenses/>.

History
=======

The Geohash encoding was originally described by Gustavo Niemeyer and
the algorithm published in the Wikipedia Geohash_ article.

This implementation of Geohashes was written by Leonard Norrgard
<leonard.norrgard@gmail.com>.

Keywords
========

Geohash, GIS, latitude, longitude, encode, decode, Galileo, GPS, WGS84, coordinates, geotagging.

.. _Geohashes: http://en.wikipedia.org/wiki/Geohash
.. _github: https://github.com/vinsci/geohash/archive/master.zip
.. _Python package index: http://pypi.python.org
.. _Geohash: http://en.wikipedia.org/wiki/Geohash

.. Local Variables:
.. mode:rst
.. End:
