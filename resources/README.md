# Resources

This directory contains the following useful resources used in this paper:

  1. WikiExtractor.py : a python script that extracts text from a Wikipedia database dump. Full details can be found [here.](https://github.com/attardi/wikiextractor)
  
  2. [MADAMIRA](http://innovation.columbia.edu/technologies/cu14012_arabic-language-disambiguation-for-natural-language-processing-applications) : an Arabic morphological analyzer and disambiguator. MADAMIRA was utilized to preprocess the text. For example, it separates words refixes, such as Al-taareef (the), and suffixes, such as possessive pronouns. Here is the command used to run MADAMIRA:
  ```
  C:\Users\oae15\Downloads\JDK64\bin\java.exe -Xmx3000m -Xms3000m -XX:NewRatio=3 -jar MADAMIRA-release-20170403-2.1.jar -rawinput "C:\Python\Python36\coding4fun\Notebooks\fastai\for research\Ar_LM\data\ASTD_text_only.txt" -rawoutdir .\samples\output -rawconfig .\samples\sampleConfigFile.xml -msaonly
  ```
  **Note:** make sure you are using JDK 64 not 32
  
  3. sampleConfigFile.xml : MADAMIRA configuration file. Make sure to use the same configuration if you want to process your own data using MADAMIRA.
  
  4. [arwiki-20190301-pages-articles-multistream.xml.bz2](https://dumps.wikimedia.org/arwiki/20190301/arwiki-20190301-pages-articles-multistream.xml.bz2) : all Arabic Wikipedia articles till March 2019. These are the articles used to train the general language model.
