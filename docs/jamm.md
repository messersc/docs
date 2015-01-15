# JAMM Galaxy integration

JAMM is a peak finder for NGS data.
doi: 10.1093/bioinformatics/btu568

## JAMM wrapper
Find it here: 
https://github.com/messersc/jamm

## Help for writing a tool definition (XML)
Every tool needs a xml defining the interface exposed to the user.

Tutorials can be found here:

https://wiki.galaxyproject.org/Admin/Tools/ToolConfigSyntax

http://saml.rilspace.com/creating-a-galaxy-tool-for-r-scripts-that-output-images-and-pdfs

http://gmod.org/wiki/Galaxy_Tutorial_2012_Extras


## Writing a wrapper

In case your tool behaves in a different way then can be handled 
by the xml alone, you will have to write an additional wrapper.

## Criteria (Do I need a wrapper)

* Input files are not passed through arguments but loaded based on predetermined fixed names
    * The wrapper can create symbolic links between the files and the predetermined fixed names in the cwd 
* Output files with conditional names are not passed through arguments
    * The wrapper can create symbolic links between the files and predetermined fixed names in the cwd 
* Using R functions
    * The wrapper can be used for libraries loading, data preprocessing and argument parsing 
* Multiple command lines
    * A simple bash wrapper can be used to pass arguments and call multiple commands

http://wiki.sb-roscoff.fr/ifb/index.php/Tool_Integration_Short_Tutorial

If you need to write a wrapper, best look at examples. You can choose e.g. between
python, perl or bash.

Examples can be found here:

https://www.e-biogenouest.org/wiki/WrapperpythonforGalaxy:Asyntaxexample

https://github.com/bgruening/galaxytools

https://github.com/peterjc/pico_galaxy/blob/master/tools/protein_analysis/README.rst