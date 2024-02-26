# Metallophore-Identification
This is a continuing project based on the simple idea of identifying all metallophore compounds in a mass spectrometry sample using simple matrix subtraction methods to get all ions matching to a certain change in mass related to a particular metal ion(s) mass.

The input is filtered to only include masses above a particular noise level and then a function is passed to search for all ions that differ, as an example, by the mass of a sodium adduct. Since sodium is one of the most common adducts it is expected to see many.

The mass of the sodium adduct is not held to a particular mass but instead passed as a lower and upper bound, allowing the mass to fluctuate with a maximum of 0.001 Da or 1 mDa. This may not be enough for lower quality mass spectrometry data, but is good enough to only get high quality matches in moderate and high quality data.

Typically for one LC-MSMS runs worth of data this function only takes about 0.5 seconds, so the matrix subtractions and mask application (using numpy) seems scalable to even thousands of LC-MSMS samples.

Currently this is reliant on the bucketting capabilities of Metaboscape (from Bruker). But the next steps (in addition to expanding to functions with more metal ions), is to make this compatable with open source formats like mzML/mzXML/mgf.

Potentially this could be applied to molecular networks as well.
