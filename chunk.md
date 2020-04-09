# How Does Do an Apertium: Transfer with Chunking

A typical translation pair which uses chunking has 3 rule files for each translation direction: `abc-xyz.t1x` is the chunking rules, `abc-xyz.t2x` is the interchunk rules, and `abc-xyz.t3x` is the postchunk rules. These can be referred to either by these names or by their file extensions.

<details>
<summary>Exercise</summary>

Try making a rule to change adjective-noun order and make adjectives agree in number.

Input: `^green<adj>/verde<adj>$ ^box<n><sg>/caja<n><f><sg>$ ^blue<adj>/azul<adj>$ ^table<n><pl>/mesa<n><f><pl>$`

Output: `^verde<adj><sg>$ ^caja<n><f><sg>$ ^azul<adj><pl>$ ^mesa<n><f><pl>$`

Note: You'll need the top of your rule file to be `<transfer default="lu">` for this to work as a stand-alone example. If you decide to test this within a pair, leave it as `<transfer default="chunk">`.

<details>
<summary>Script to run</summary>

```bash
#!/bin/bash

apertium-preprocess-transfer test.t1x test.bin
echo "^green<adj>/verde<adj>$ ^box<n><sg>/caja<n><f><sg>$ ^blue<adj>/azul<adj>$ ^table<n><pl>/mesa<n><f><pl>$" | apertium-transfer -b test.t1x test.bin
```

</details>

<details>
<summary>Solution</summary>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<transfer default="lu">
  <section-def-cats>
    <def-cat n="nom">
      <cat-item tags="n.*"/>
    </def-cat>
    <def-cat n="adj">
      <!-- match regardless of whether adjectives have other tags -->
      <cat-item tags="adj"/>
      <cat-item tags="adj.*"/>
    </def-cat>
  </section-def-cats>

  <section-def-attrs>
    <def-attr n="nbr">
      <attr-item tags="sg"/>
      <attr-item tags="pl"/>
    </def-attr>
  </section-def-attrs>

  <section-rules>
    <rule comment="REGLA: adj n -> n adj">
      <pattern>
        <pattern-item n="adj"/>
        <pattern-item n="nom"/>
      </pattern>
      <action>
        <out>
          <lu>
            <clip pos="2" side="tl" part="whole"/>
          </lu>
          <b/>
          <lu>
            <clip pos="1" side="tl" part="whole"/>
            <clip pos="2" side="tl" part="nbr"/>
          </lu>
        </out>
      </action>
    </rule>
  </section-rules>
</transfer>
```

</details>

</details>


