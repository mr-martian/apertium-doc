# How Does Do an Apertium: The Pipeline

From the perspective of your computer, Apertium is actually a fairly simple program. The program called `apertium` is really just a shell script whose fundamental job is to locate and run other shell scripts. The job of an Apertium translation pair is to create a shell script that will translate things when `apertium` runs it.

So how do these scripts get set up? Each language module and translation pair has a file called `modes.xml` which contains entries that look like this:

```xml
  <mode name="wad-tagger">
    <pipeline>
      <program name="lt-proc -w">
        <file name="wad.automorf.bin"/>
      </program>
      <program name="cg-proc -w -1 -n">
        <file name="wad.rlx.bin"/>
      </program>
    </pipeline>
  </mode>
```

This will get converted into the file `modes/wad-tagger.mode` which looks like this:

```bash
lt-proc -w '/usr/local/share/apertium/apertium-wad/wad.automorf.bin' | cg-proc -w -1 -n '/usr/local/share/apertium/apertium-wad/wad.rlx.bin'
```


