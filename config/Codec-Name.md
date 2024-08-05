
 
Audio and video files, as well as other data streams can be encoded and decoded using a certain codec. Files are typically encoded in order to transmit or save them in a secure way. Thus, in order to view or play the file or stream, the same codec is needed for decoding.
 
**Download ->->->-> [https://oraselic.blogspot.com/?d=2A0SF7](https://oraselic.blogspot.com/?d=2A0SF7)**


 
This module defines base classes for standard Python codecs (encoders anddecoders) and provides access to the internal Python codec registry, whichmanages the codec and error handling lookup process. Most standard codecsare text encodings, which encode text to bytes (anddecode bytes to text), but there are also codecs provided that encode text totext, and bytes to bytes. Custom codecs may encode and decode between arbitrarytypes, but some module features are restricted to be used specifically withtext encodings or with codecs that encode tobytes.
 
Errors may be given to set the desired error handling scheme. Thedefault error handler is 'strict' meaning that encoding errors raiseValueError (or a more codec specific subclass, such asUnicodeEncodeError). Refer to Codec Base Classes for moreinformation on codec error handling.
 
Errors may be given to set the desired error handling scheme. Thedefault error handler is 'strict' meaning that decoding errors raiseValueError (or a more codec specific subclass, such asUnicodeDecodeError). Refer to Codec Base Classes for moreinformation on codec error handling.
 
The stateless encoding and decoding functions. These must befunctions or methods which have the same interface asthe encode() and decode() methods of Codecinstances (see Codec Interface).The functions or methods are expected to work in a stateless mode.

Incremental encoder and decoder classes or factory functions.These have to provide the interface defined by the base classesIncrementalEncoder and IncrementalDecoder,respectively. Incremental codecs can maintain state.
 
Register a codec search function. Search functions are expected to take oneargument, being the encoding name in all lower case letters with hyphensand spaces converted to underscores, and return a CodecInfo object.In case a search function cannot find a given encoding, it should returnNone.
 
While the builtin open() and the associated io module are therecommended approach for working with encoded text files, this moduleprovides additional utility functions and classes that allow the use of awider range of codecs when working with binary files:
 
If encoding is not None, then theunderlying encoded files are always opened in binary mode.No automatic conversion of '\n' is done on reading and writing.The mode argument may be any binary mode acceptable to the built-inopen() function; the 'b' is automatically added.
 
encoding specifies the encoding which is to be used for the file.Any encoding that encodes to and decodes from bytes is allowed, andthe data types supported by the file methods depend on the codec used.
 
Data written to the wrapped file is decoded according to the givendata\_encoding and then written to the original file as bytes usingfile\_encoding. Bytes read from the original file are decodedaccording to file\_encoding, and the result is encodedusing data\_encoding.
 
Uses an incremental encoder to iteratively encode the input provided byiterator. This function is a generator.The errors argument (as well as anyother keyword argument) is passed through to the incremental encoder.
 
Uses an incremental decoder to iteratively decode the input provided byiterator. This function is a generator.The errors argument (as well as anyother keyword argument) is passed through to the incremental decoder.
 
Each codec has to define four interfaces to make it usable as codec in Python:stateless encoder, stateless decoder, stream reader and stream writer. Thestream reader and writers typically reuse the stateless encoder/decoder toimplement the file protocols. Codec authors also need to define how thecodec will handle encoding and decoding errors.
 
Replace with backslashed escape sequences.On encoding, use hexadecimal form of Unicodecode point with formats \xhh\uxxxx \Uxxxxxxxx.On decoding, use hexadecimal form of bytevalue with format \xhh.Implemented inbackslashreplace\_errors().
 
On decoding, replace byte with individualsurrogate code ranging from U+DC80 toU+DCFF. This code will then be turnedback into the same byte when the'surrogateescape' error handler is usedwhen encoding the data. (See **PEP 383** formore.)
 
Register the error handling function error\_handler under the name name.The error\_handler argument will be called during encoding and decodingin case of an error, when name is specified as the errors parameter.
 
For encoding, error\_handler will be called with a UnicodeEncodeErrorinstance, which contains information about the location of the error. Theerror handler must either raise this or a different exception, or return atuple with a replacement for the unencodable part of the input and a positionwhere encoding should continue. The replacement may be either str orbytes. If the replacement is bytes, the encoder will simply copythem into the output buffer. If the replacement is a string, the encoder willencode the replacement. Encoding continues on original input at thespecified position. Negative position values will be treated as beingrelative to the end of the input string. If the resulting position is out ofbound an IndexError will be raised.
 
Decoding and translating works similarly, except UnicodeDecodeError orUnicodeTranslateError will be passed to the handler and that thereplacement from the error handler will be put into the output directly.
 
Malformed data is replaced by a backslashed escape sequence.On encoding, use the hexadecimal form of Unicode code point with formats\xhh \uxxxx \Uxxxxxxxx.On decoding, use the hexadecimal form ofbyte value with format \xhh.
 
The unencodable character is replaced by a \N... escape sequence. Theset of characters that appear in the braces is the Name property fromUnicode Character Database. For example, the German lowercase letter ''will be converted to byte sequence \NLATIN SMALL LETTER SHARP S .
 
Encodes the object input and returns a tuple (output object, length consumed).For instance, text encoding convertsa string object to a bytes object using a particularcharacter set encoding (e.g., cp1252 or iso-8859-1).
 
Decodes the object input and returns a tuple (output object, lengthconsumed). For instance, for a text encoding, decoding convertsa bytes object encoded using a particularcharacter set encoding to a string object.
 
The IncrementalEncoder class is used for encoding an input in multiplesteps. It defines the following methods which every incremental encoder mustdefine in order to be compatible with the Python codec registry.
 
The errors argument will be assigned to an attribute of the same name.Assigning to this attribute makes it possible to switch between different errorhandling strategies during the lifetime of the IncrementalEncoderobject.
 
Return the current state of the encoder which must be an integer. Theimplementation should make sure that 0 is the most commonstate. (States that are more complicated than integers can be convertedinto an integer by marshaling/pickling the state and encoding the bytesof the resulting string into an integer.)
 
The IncrementalDecoder class is used for decoding an input in multiplesteps. It defines the following methods which every incremental decoder mustdefine in order to be compatible with the Python codec registry.
 
The errors argument will be assigned to an attribute of the same name.Assigning to this attribute makes it possible to switch between different errorhandling strategies during the lifetime of the IncrementalDecoderobject.
 
Return the current state of the decoder. This must be a tuple with twoitems, the first must be the buffer containing the still undecodedinput. The second must be an integer and can be additional stateinfo. (The implementation should make sure that 0 is the most commonadditional state info.) If this additional state info is 0 it must bepossible to set the decoder to the state which has no input buffered and0 as the additional state info, so that feeding the previouslybuffered input to the decoder returns it to the previous state withoutproducing any output. (Additional state info that is more complicated thanintegers can be converted into an integer by marshaling/pickling the infoand encoding the bytes of the resulting string into an integer.)
 
The errors argument will be assigned to an attribute of the same name.Assigning to this attribute makes it possible to switch between different errorhandling strategies during the lifetime of the StreamWriter object.
 
Writes the concatenated iterable of strings to the stream (possibly by reusingthe write() method). Infinite orvery large iterables are not supported. The standard bytes-to-bytes codecsdo not support this method.
 
The errors argument will be assigned to an attribute of the same name.Assigning to this attribute makes it possible to switch between different errorhandling strategies during the lifetime of the StreamReader object.
 
The chars argument indicates the number of decodedcode points or bytes to return. The read() method willnever return more data than requested, but it might return less,if there is not enough available.
 
The size argument indicates the approximate maximumnumber of encoded bytes or code points to readfor decoding. The decoder can modify this setting asappropriate. The default value -1 indicates to read and decode as much aspossible. This parameter is intended toprevent having to decode huge files in one step.
 
The method should use a greedy read strategy meaning that it should readas much data as is allowed within the definition of the encoding and thegiven size, 