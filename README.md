# Character-Complexity
Calculate and compare complexity of Unicode characters in multiple texts in multiple languages

Texts for analysis should be in UTF-8 .txt format, in one folder
	Specify location in Text_Parser.ipynb

Extract_text_from_pdf.ipynb can be used to convert PDF files to text files, examples in Test-Files
Some PDF files are images and require different processing to be converted: so far Hindi and Hebrew gave unresolved issues

Code:

Batch_run.ipynb
        runs all scripts
          If first time running, specify:
            run_one_time_setup = True
            
Run once: "run_one_time_setup" scripts:
Build_Unicode_Database.ipynb
          builds database of Unicode characters
          output: unicode_character_database.pkl
Assign_fonts.ipynb
          builds database of Noto fonts assigned to Unicode characters
          can be updated to use other fonts but Noto is currently default for entire pipeline
          input: unicode_character_database.pkl
          output: noto_font_table.pkl and unicode_to_notofonts_map.pkl
Glyph_Complexity_Database.ipynb
          builds database of calculated complexity per glyph represented by Unicode, per font
          
Run per folder of text files:
Text_Parser.ipynb
          Applies complexity per glyph to entire text
          Calculates complexity of entire text
          Compare complexity of texts across languages 
