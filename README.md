EME for Go [![Build Status](https://drone.io/github.com/rfjakob/eme/status.png)](https://drone.io/github.com/rfjakob/eme/latest) [![GoDoc](https://godoc.org/github.com/rfjakob/eme?status.svg)](https://godoc.org/github.com/rfjakob/eme)
==========

EME (ECB-Mix-ECB) is a wide-block encryption mode developed by Halevi
and Rogaway in 2003 [eme].

EME uses multiple invocations of a block cipher to construct a new
cipher of bigger block size (in multiples of 16 bytes, up to 2048 bytes).

This is an implementation of EME in Go.

Is it patentend?
----------------

In 2007, the UC Davis has decided to abandon [patabandon] the patent
application for EME [patappl].

Related algorithms
------------------

**EME-32** is EME with the cipher set to AES and the length set to 512.
That is, EME-32 [eme-32-pdf] is a subset of EME.

**EME2**, also known as EME* [emestar], is an extended version of EME
that has built-in handling for data that is not a multiple of 16 bytes
long.  
EME2 has been selected for standardization in IEEE P1619.2 [p1619.2].

References
----------

**[eme]** *A Parallelizable Enciphering Mode*  
Shai Halevi, Phillip Rogaway, 28 Jul 2003  
https://eprint.iacr.org/2003/147.pdf  
Note: This is the original EME paper. EME is specified for an arbitrary
number of block-cipher blocks. EME-32 is a concrete implementation of
EME with a fixed length of 32 AES blocks.

**[eme-32-email]** *Re: EME-32-AES with editorial comments*  
Shai Halevi, 07 Jun 2005  
http://grouper.ieee.org/groups/1619/email/msg00310.html

**[eme-32-pdf]** *Draft Standard for Tweakable Wide-block Encryption*  
Shai Halevi, 02 June 2005  
http://grouper.ieee.org/groups/1619/email/pdf00020.pdf  
Note: This is the latest version of the EME-32 draft that I could find. It
includes test vectors and C source code.

**[eme-32-testvec]** *Re: Test vectors for LRW and EME*  
Shai Halevi, 16 Nov 2004  
http://grouper.ieee.org/groups/1619/email/msg00218.html

**[emestar]** _EME*: extending EME to handle arbitrary-length
messages with associated data_  
Shai Halevi, 27 May 2004  
https://eprint.iacr.org/2004/125.pdf

**[patabandon]** *Re: [P1619-2] Non-awareness patent statement made by UC Davis*  
Mat Ball, 26 Nov 2007  
http://grouper.ieee.org/groups/1619/email-2/msg00005.html

**[patappl]** *Block cipher mode of operation for constructing a wide-blocksize block cipher from a conventional block cipher*  
US patent application US20040131182  
http://www.google.com/patents/US20040131182

**[p1619.2]** *IEEE P1619.2™/D9 Draft Standard for Wide-Block  
Encryption for Shared Storage Media*  
IEEE, Dec 2008  
http://siswg.net/index2.php?option=com_docman&task=doc_view&gid=156&Itemid=41  
Note: This is a draft version. The final version is not freely available
and must be bought from IEEE.
