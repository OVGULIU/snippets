---
category: reveal.js
title: 'Revealize'
type: 'python'
---

### Get reveal.js sections

for a series of PPT slides saved as images

{% highlight python %}

import glob
import os
import re

dirName = '/path/to/images/folder'
prefix = 'Slide' # default for PowerPoint

outFileName = '_slides.md'

os.chdir(dirName)

files2search = '*.*'
slides = glob.glob(files2search)
slides.sort()

path = 'online/images/folder/'
ext = '.PNG'
jstext = ''

for i,fn in enumerate(slides):

    fn, ext = os.path.splitext(fn)
    jstext += '\n<section data-background="%s%s%d%s" data-background-size="contain">\n</section>\n' % (path,prefix,i+1,ext)

with open (outFileName, 'w') as outFile:
    outFile.write(jstext)

{% endhighlight %}
