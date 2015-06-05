hdffxvrt is a shell script wrapper for FFMPEG to convert M2TS HD-Video to editable Quicktime MOV files.

For introductory discussion, see the blog post at http://www.crypticide.com/dropsafe/article/2657

Download via subversion using the information on the "Source" tab, or access it directly at http://hdffxvrt.googlecode.com/svn/trunk/hdffxvrt

Usage:
```
    hdffxvrt [options] filename.mts ...
```

Options:
```
    -d         # enables debugging
    -p PRESET  # enables PRESET settings, below
    -i SIZE    # specify raw input size
    -x         # create output in current working directory
```

Presets:
```
    thumb      # 320x180 mpeg4 + aac audio (10 second thumbnail)
    small      # 640x360 mpeg4 + aac audio
    medium     # 1280x720 mpeg4 + aac audio (default)
    large      # 1366x768 mpeg4 + aac audio
    huge       # 1920x1080 mpeg4 + aac audio (very silly)
    edit-mp4   # 1280x720 mpeg4 keyframes + raw audio
    edit-mj    # 1280x720 mjpeg + raw audio
    edit       # shorthand for 'edit-mj'
```

Examples:

> Convert MTS files to 720p suitable for iMovie editing

> ` hdffxvrt -p edit *.mts `

> Create short 'video thumbnails' as an aide-memoire

> ` hdffxvrt -p thumb *.mts `

> Convert stuff from another disk or server, put in current directory

> ` hdffxvrt -x -p small /somewhere/else/*.mts `

Basic file locking is performed upon the output file so that on multi-core machines, multiple instances of hdffxvrt can be run in parallel in separate shells, to take maximum advantage of multiple cpus/cores.

I recommend storing the original MTS files, as they are going to be
much smaller than anything of comparable quality that ffmpeg produces.

See the project homepage at http://code.google.com/p/hdffxvrt/ for documentation, wiki and updates.