#IBCM Assembler
This program converts assembly like code into IBCM hex. You can find information on IBCM (Itty Bitty Computing Machine) [here](http://aaronbloomfield.github.io/pdr/ibcm/ibcm.html).

##Usage
`assemble.py` can take one or two command line arguments. The first argument is the name of the file to be translated, this is not optional. The second argument is name of the output file, this is optional and will default to `out.ibcm` if no arguement is provided.

###Example Usage
`python assemble.py foo.iacm bar.ibcm`
This command reads `foo.iacm` and writes the hex values to `bar.ibcm`.

`python assemble.py baz.iacm`
This command will read in `baz.iacm` and write the hex values to `out.ibcm`.

`python assemble.py bar.ibcm foo.iacm`
This will read in `bar.ibcm` and write to `foo.iacm`. Note that if `bar.ibcm` is in proper `.ibcm` format then the program will likely crash or produce junk in `foo.iacm`.

###`.iacm` advantages
`.iacm` implements variables and labels, allowing the programmer to remember names instead of memory addresses, the assembler takes care of replacing the human readable names with the appropriate addresses. This also means that when extra variables or lines or code are added, the programmer does not need to worry about variable and label addresses changing. The biggest advantage of writing in `.iacm` is being able to use english commands like `load` and `add` as opposed to `3xxx` and `5xxx`.