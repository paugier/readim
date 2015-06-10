
Overview
========
ReadIM is a c++ wrapper to load DaVis Images and Vectors DaVis V8.
ReadIM is a 'low level' interface to C++ libraries provided by LaVision GMBH.

Installation
============
The libraries have been compiled succesfully on Windows platforms with 64-bit and 32-bit python.
Successfully installed with latest 32 and 64 bit versions of WinPython including:

2.7, 3.3 and 3.4

>>> python setup.py build install

Alternatively you can install a precompiled binary from the downloads page.


Usage
=====

To load a .vc7 file run::

    >>> vbuff, vatts   =  ReadIM.extra.get_Buffer_andAttributeList('filename.vc7')
    >>> v_array, vbuff = ReadIM.extra.buffer_as_array(vbuff)

similarly for a .im7 file run::

    >>> vbuff, vatts   =  ReadIM.extra.get_Buffer_andAttributeList('filename.im7')
    >>> v_array, vbuff = ReadIM.extra.buffer_as_array(vbuff)


Writing files
-------------
>>> atts = ReadIM.load_AttributeList({'attribute':'value'})
>>> ReadIM.WriteIM7('saved_file.im7', True, buff, atts.next)

Finally, memory cleanup is not automatic. To prevent manual garbarge collection do the following:

>>> del(vbuff)
>>> ReadIM.DestroyBuffer(buff)
>>> ReadIM.DestroyAttributeListSafe(atts)


For higher level access to DaVis files the IM package is available at:
https://bitbucket.org/fleming79/im
