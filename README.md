ParanoiDF
=========

The swiss army knife of PDF Analysis Tools. Based on peepdf - http://peepdf.eternal-todo.com. This README builds on the peepdf README.

![](http://i16.photobucket.com/albums/b37/psynto/1-1.jpg)

Home Page 
-----------

* https://github.com/patrickdw123/ParanoiDF
* patrickdw123(at)gmail(dot)com
* http://uk.linkedin.com/pub/patrick-wragg/8a/a7a/324/

Features
-----------

See https://github.com/patrickdw123/ParanoiDF/wiki.

Dependancies
-----------

* In order to crack passwords: 
	- PdfCrack needed (apt-get install pdfcrack)
* In order to remove DRM (editing, copying Etc.): 
	- Calibre's ebook-convert needed (apt-get install calibre)
* In order to decrypt PDFs: 
	- qpdf needed (apt-get install qpdf)
* In order to use the command redact:
	- NLTK (Natural Language ToolKit) needed (apt-get install python-nltk)
	- Java (Stanford parser is written in Java) needed (apt-get install default-jre)
* To support XML output "lxml" is needed:
   - http://lxml.de/installation.html
* Included modules: lzw, colorama, jsbeautifier, ccitt, pythonaes (Thanks to all the developers!!)

Installation
-----------

No installation is needed apart of the commented dependencies, just execute:

	python paranoiDF.py

Execution
-----------

There are two important options when ParanoidF is executed:

-f: Ignores the parsing errors. Analysing malicious files propably leads to parsing errors, so this parameter should be set.
-l: Sets the loose mode, so does not search for the endobj tag because it's not obligatory. Helpful with malformed files.


* Simple execution

Shows the statistics of the file after being decoded/decrypted and analysed:

    python paranoiDF.py [options] pdf_file


* Interactive console

Executes the interactive console, giving a wide range of tools to play with.

    python paranoiDF.py -i 


* Batch execution

It's possible to use a commands file to specify the commands to be executed in the batch mode. This type of execution is good to automatise analysis of several files:

    python paranoiDF.py [options] -s script_file 

Some Hints
-----------
If the information shown when a PDF file is parsed is not enough to know if it's harmful or not, the following commands can help to do it:

* tree

Shows the tree graph of the file or specified version. Here we can see suspicious elements.


* offsets 

Shows the physical map of the file or the specified version of the document. This is helpful to see unusual big objects or big spaces between objects.


* search

Search the specified string or hexadecimal string in the objects (decoded and encrypted streams included).


* object/rawobject

Shows the (raw) content of the object.


* stream/rawstream

Shows the (raw) content of the stream.

TODO
----------
* Refine and test redaction thresholds.
* Add automation of retrieval of redaction box information such as font size, font and redaction box coordinates.
* Add a GUI.
* Add other encryption algorithms (such as the AES).
* Digital Signatures analysis.



Bugs
----------

Feel free to send bugs/criticisms/praises/comments to patrickdw123(at)gmail(dot)com.


Google analytics script

<script>
(function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
(i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
})(window,document,'script','//www.google-analytics.com/analytics.js','ga');
ga('create', 'UA-53766717-1', 'auto');
ga('send', 'pageview');
</script>
