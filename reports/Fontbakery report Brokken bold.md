# Fontbakery report on Brokken bold

 >> com.google.fonts/check/alt_caron
    Check accent of Lcaron, dcaron, lcaron, tcaron
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    Lcaron, dcaron, lcaron, tcaron should NOT be composed with quoteright or quotesingle or comma or caron(comb). It should be composed with a distinctive glyph       
    which doesn't look like an apostrophe.                                                                                                                             
                                                                                                                                                                       
    Source: https://ilovetypography.com/2009/01/24/on-diacritics/ http://diacritics.typo.cz/index.php?id=5 https://www.typotheque.com/articles/lcaron                  
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/issues/3308

    WARN Lcaron is decomposed and therefore could not be checked. Please check manually. [code: decomposed-outline]                                                    
    WARN dcaron is decomposed and therefore could not be checked. Please check manually. [code: decomposed-outline]                                                    
    WARN lcaron is decomposed and therefore could not be checked. Please check manually. [code: decomposed-outline]                                                    
    WARN tcaron is decomposed and therefore could not be checked. Please check manually. [code: decomposed-outline]                                                    

    Result: WARN

 >> com.google.fonts/check/case_mapping
    Ensure the font supports case swapping for all its glyphs.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    Ensure that no glyph lacks its corresponding upper or lower counterpart (but only when unicode supports case-mapping).                                             
                                                                                                                                                                       
    More info: https://github.com/googlefonts/fontbakery/issues/3230

    FAIL The following glyphs lack their case-swapping counterparts:                                                                                                   
                                                                                                                                                                       
                                                                                                                                                                       
           Glyph present in the font                 Missing case-swapping counterpart                                                                                 
          ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━                                                                        
           U+01F5: LATIN SMALL LETTER G WITH ACUTE   U+01F4: LATIN CAPITAL LETTER G WITH ACUTE                                                                         
                                                                                                                                                                       
                                                                                                                                                                       
         [code: missing-case-counterparts]                                                                                                                             

# Result: FAIL

 >> com.google.fonts/check/contour_count
    Check if each glyph has the recommended amount of contours.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    Visually QAing thousands of glyphs by hand is tiring. Most glyphs can only be constructured in a handful of ways. This means a glyph's contour count will only     
    differ slightly amongst different fonts, e.g a 'g' could either be 2 or 3 contours, depending on whether its double story or single story.                         
                                                                                                                                                                       
    However, a quotedbl should have 2 contours, unless the font belongs to a display family.                                                                           
                                                                                                                                                                       
    This check currently does not cover variable fonts because there's plenty of alternative ways of constructing glyphs with multiple outlines for each feature in a  
    VarFont. The expected contour count data for this check is currently optimized for the typical construction of glyphs in static fonts.                             
                                                                                                                                                                       
    WARN This check inspects the glyph outlines and detects the total number of contours in each of them. The expected values are infered from the typical ammounts    
         of contours observed in a large collection of reference font families. The divergences listed below may simply indicate a significantly different design on   
         some of your glyphs. On the other hand, some of these may flag actual bugs in the font such as glyphs mapped to an incorrect codepoint. Please consider       
         reviewing the design and codepoint assignment of these to make sure they are correct.                                                                         
                                                                                                                                                                       
         The following glyphs do not have the recommended number of contours:                                                                                          
                                                                                                                                                                       
                                                                                                                                                                       
          - Glyph name: uni01F5   Contours detected: 4    Expected: 3                                                                                                  
                                                                                                                                                                       
                                                                                                                                                                       
         [code: contour-count]                                                                                                                                         

    Result: WARN

 >> com.google.fonts/check/family/win_ascent_and_descent
    Checking OS/2 usWinAscent & usWinDescent.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    A font's winAscent and winDescent values should be greater than or equal to the head table's yMax, abs(yMin) values. If they are less than these values, clipping  
    can occur on Windows platforms (https://github.com/RedHatBrand/Overpass/issues/33).                                                                                
                                                                                                                                                                       
    If the font includes tall/deep writing systems such as Arabic or Devanagari, the winAscent and winDescent can be greater than the yMax and absolute yMin values    
    to accommodate vowel marks.                                                                                                                                        
                                                                                                                                                                       
    When the 'win' Metrics are significantly greater than the UPM, the linespacing can appear too loose. To counteract this, enabling the OS/2 fsSelection bit 7       
    (Use_Typo_Metrics), will force Windows to use the OS/2 'typo' values instead. This means the font developer can control the linespacing with the 'typo' values,    
    whilst avoiding clipping by setting the 'win' values to values greater than the yMax and absolute yMin.                                                            
                                                                                                                                                                       
    FAIL OS/2.usWinAscent value should be equal or greater than 991, but got 990 instead [code: ascent]                                                                

# Result: FAIL

 >> com.google.fonts/check/linegaps
    Checking Vertical Metric Linegaps.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    The LineGap value is a space added to the line height created by the union of the (typo/hhea)Ascender and (typo/hhea)Descender. It is handled differently          
    according to the environment.                                                                                                                                      
                                                                                                                                                                       
    This leading value will be added above the text line in most desktop apps. It will be shared above and under in web browsers, and ignored in Windows if            
    Use_Typo_Metrics is disabled.                                                                                                                                      
                                                                                                                                                                       
    For better linespacing consistency across platforms, (typo/hhea)LineGap values must be 0.                                                                          
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/issues/4133
               https://googlefonts.github.io/gf-guide/metrics.html

    FAIL hhea lineGap is not equal to 0.                                                                                                                               
                                                                                                                                                                       
         Overridden: This check was originally a WARN but was overridden by the ufo profile: For Google Fonts, all messages from this check are considered FAILs.      
         [code: hhea]                                                                                                                                                  

# Result: FAIL

 >> com.google.fonts/check/math_signs_width
    Check math signs have the same width.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    It is a common practice to have math signs sharing the same width (preferably the same width as tabular figures accross the entire font family).                   
                                                                                                                                                                       
    This probably comes from the will to avoid additional tabular math signs knowing that their design can easily share the same width.                                
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/issues/3832

    WARN The most common width is 560 among a set of 2 math glyphs. The following math glyphs have a different width, though:                                          
                                                                                                                                                                       
         Width = 397: plus                                                                                                                                             
                                                                                                                                                                       
         Width = 480: equal                                                                                                                                            
                                                                                                                                                                       
         Width = 429: minus [code: width-outliers]                                                                                                                     

    Result: WARN

 >> com.google.fonts/check/whitespace_glyphs
    Font contains glyphs for whitespace characters?
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    The OpenType specification recommends that fonts should contain glyphs for the following whitespace characters:                                                    
                                                                                                                                                                       
    - U+0020 SPACE - U+00A0 NO-BREAK SPACE                                                                                                                             
                                                                                                                                                                       
    The space character is required for text processing, and the no-break space is useful to prevent line breaks at its position. It is also recommended to have a     
    glyph for the tab character (U+0009) and the soft hyphen (U+00AD), but these are not mandatory.                                                                    
                                                                                                                                                                       
    FAIL Whitespace glyph missing for codepoint 0x00A0. [code: missing-whitespace-glyph-0x00A0]                                                                        

# Result: FAIL

 >> com.google.fonts/check/outline_jaggy_segments
    Do outlines contain any jaggy segments?
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    This check heuristically detects outline segments which form a particularly small angle, indicative of an outline error. This may cause false positives in cases   
    such as extreme ink traps, so should be regarded as advisory and backed up by manual inspection.                                                                   
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/issues/3064

    WARN The following glyphs have jaggy segments:                                                                                                                     
                                                                                                                                                                       
                                                                                                                                                                       
          * P (U+0050): L<<175.0,534.0>--<174.0,534.0>>/L<<174.0,534.0>--<255.0,520.0>> = 9.80609275989708                                                             
                                                                                                                                                                       
          * T_T: L<<370.0,1.0>--<252.0,0.0>>/L<<252.0,0.0>--<252.0,0.0>> = 0.48554583000816465                                                                         
                                                                                                                                                                       
          * Z (U+005A): L<<392.0,571.0>--<393.0,571.0>>/L<<393.0,571.0>--<232.0,598.0>> = 9.520021865774119                                                            
                                                                                                                                                                       
          * Zacute (U+0179): L<<392.0,571.0>--<393.0,571.0>>/L<<393.0,571.0>--<232.0,598.0>> = 9.520021865774119                                                       
                                                                                                                                                                       
          * Zcaron (U+017D): L<<392.0,571.0>--<393.0,571.0>>/L<<393.0,571.0>--<232.0,598.0>> = 9.520021865774119                                                       
                                                                                                                                                                       
          * Zdotaccent (U+017B): L<<392.0,571.0>--<393.0,571.0>>/L<<393.0,571.0>--<232.0,598.0>> = 9.520021865774119                                                   
                                                                                                                                                                       
          * section (U+00A7): L<<94.0,225.0>--<98.0,226.0>>/L<<98.0,226.0>--<94.0,226.0>> = 14.036243467926484 [code: found-jaggy-segments]                            
                                                                                                                                                                       

    Result: WARN

 >> com.google.fonts/check/outline_semi_vertical
    Do outlines contain any semi-vertical or semi-horizontal lines?
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    This check detects line segments which are nearly, but not quite, exactly horizontal or vertical. Sometimes such lines are created by design, but often they are   
    indicative of a design error.                                                                                                                                      
                                                                                                                                                                       
    This check is disabled for italic styles, which often contain nearly-upright lines.                                                                                
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/pull/3088

    WARN The following glyphs have semi-vertical/semi-horizontal lines:                                                                                                
                                                                                                                                                                       
                                                                                                                                                                       
          * A (U+0041): L<<386.0,217.0>--<232.0,218.0>>                                                                                                                
                                                                                                                                                                       
          * A.ss02: L<<662.0,261.0>--<661.0,127.0>>                                                                                                                    
                                                                                                                                                                       
          * Aacute (U+00C1): L<<386.0,217.0>--<232.0,218.0>>                                                                                                           
                                                                                                                                                                       
          * Aacute.ss02: L<<662.0,261.0>--<661.0,127.0>>                                                                                                               
                                                                                                                                                                       
          * Abreve (U+0102): L<<386.0,217.0>--<232.0,218.0>>                                                                                                           
                                                                                                                                                                       
          * Abreve.ss02: L<<662.0,261.0>--<661.0,127.0>>                                                                                                               
                                                                                                                                                                       
          * Acircumflex (U+00C2): L<<386.0,217.0>--<232.0,218.0>>                                                                                                      
                                                                                                                                                                       
          * Acircumflex.ss02: L<<662.0,261.0>--<661.0,127.0>>                                                                                                          
                                                                                                                                                                       
          * Adieresis (U+00C4): L<<386.0,217.0>--<232.0,218.0>>                                                                                                        
                                                                                                                                                                       
          * Adieresis.ss02: L<<662.0,261.0>--<661.0,127.0>>                                                                                                            
                                                                                                                                                                       
          * 260 more.                                                                                                                                                  
                                                                                                                                                                       
                                                                                                                                                                       
         Use -F or --full-lists to disable shortening of long lists. [code: found-semi-vertical]                                                                       

    Result: WARN

 >> com.google.fonts/check/dotted_circle
    Ensure dotted circle glyph is present and can attach marks.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    The dotted circle character (U+25CC) is inserted by shaping engines before mark glyphs which do not have an associated base, especially in the context of broken   
    syllabic clusters.                                                                                                                                                 
                                                                                                                                                                       
    For fonts containing combining marks, it is recommended that the dotted circle character be included so that these isolated marks can be displayed properly; for   
    fonts supporting complex scripts, this should be considered mandatory.                                                                                             
                                                                                                                                                                       
    Additionally, when a dotted circle glyph is present, it should be able to display all marks correctly, meaning that it should contain anchors for all attaching    
    marks.                                                                                                                                                             
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/issues/3600

    WARN No dotted circle glyph present [code: missing-dotted-circle]                                                                                                  

    Result: WARN

  0%|                                                                                                                                      | 0/8248819 [00:00<?, ?it/s]
  0%|                                                                                                                             | 4.00k/7.87M [00:00<03:42, 37.0kB/s]
  0%|5                                                                                                                             | 36.0k/7.87M [00:00<00:47, 171kB/s]
  1%|#3                                                                                                                            | 84.0k/7.87M [00:00<00:29, 276kB/s]
  2%|###                                                                                                                            | 196k/7.87M [00:00<00:15, 530kB/s]
  5%|######3                                                                                                                        | 404k/7.87M [00:00<00:08, 954kB/s]
 10%|############8                                                                                                                 | 820k/7.87M [00:00<00:04, 1.74MB/s]
 20%|#########################3                                                                                                   | 1.60M/7.87M [00:00<00:01, 3.30MB/s]
 41%|##################################################9                                                                          | 3.21M/7.87M [00:01<00:00, 6.30MB/s]
 79%|##################################################################################################6                          | 6.21M/7.87M [00:01<00:00, 12.8MB/s]
100%|############################################################################################################################6| 7.85M/7.87M [00:01<00:00, 14.0MB/s]
100%|#############################################################################################################################| 7.87M/7.87M [00:01<00:00, 6.76MB/s]

 >> com.google.fonts/check/soft_dotted
    Ensure soft_dotted characters lose their dot when combined with marks that replace the dot.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    An accent placed on characters with a "soft dot", like i or j, causes the dot to disappear. An explicit dot above can be added where required. See "Diacritics on  
    i and j" in Section 7.1, "Latin" in The Unicode Standard.                                                                                                          
                                                                                                                                                                       
    Characters with the Soft_Dotted property are listed in https://www.unicode.org/Public/UCD/latest/ucd/PropList.txt                                                  
                                                                                                                                                                       
    See also: https://googlefonts.github.io/gf-guide/diacritics.html#soft-dotted-glyphs                                                                                
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/issues/4059

    WARN The dot of soft dotted characters used in orthographies must disappear in the following strings: į̀ į́ į̂ į̃ į̄ į̌                                                  
                                                                                                                                                                       
         The dot of soft dotted characters should disappear in other cases, for example: į̆ į̇ į̈ į̊ į̋ į̦̀ į̦́ į̦̂ į̦̃ į̦̄ į̦̆ į̦̇ į̦̈ į̦̊ į̦̋ į̦̌ į̧̀ į̧́ į̧̂ į̧̃                                       
                                                                                                                                                                       
         Your font fully covers the following languages that require the soft-dotted feature: Lithuanian (Latn, 2,357,094 speakers).                                   
                                                                                                                                                                       
         Your font does not cover the following languages that require the soft-dotted feature: Gulay (Latn, 250,478 speakers), Fur (Latn, 1,230,163 speakers),        
         Ukrainian (Cyrl, 29,273,587 speakers), Cicipu (Latn, 44,000 speakers), Ebira (Latn, 2,200,000 speakers), Ejagham (Latn, 120,000 speakers), Sar (Latn,         
         500,000 speakers), Belarusian (Cyrl, 10,064,517 speakers), Lugbara (Latn, 2,200,000 speakers), Basaa (Latn, 332,940 speakers), Kpelle, Guinea (Latn, 622,000  
         speakers), Igbo (Latn, 27,823,640 speakers), Dan (Latn, 1,099,244 speakers), Avokaya (Latn, 100,000 speakers), Ma’di (Latn, 584,000 speakers), Mango (Latn,   
         77,000 speakers), Bafut (Latn, 158,146 speakers), Mundani (Latn, 34,000 speakers), Kom (Latn, 360,685 speakers), Southern Kisi (Latn, 360,000 speakers),      
         Makaa (Latn, 221,000 speakers), Vute (Latn, 21,000 speakers), Zapotec (Latn, 490,000 speakers), Ekpeye (Latn, 226,000 speakers), Aghem (Latn, 38,843          
         speakers), Koonzime (Latn, 40,000 speakers), Nzakara (Latn, 50,000 speakers), Yala (Latn, 200,000 speakers), Ngbaka (Latn, 1,020,000 speakers), South         
         Central Banda (Latn, 244,000 speakers), Dii (Latn, 71,000 speakers), Nateni (Latn, 100,000 speakers), Bete-Bendi (Latn, 100,000 speakers), Navajo (Latn,      
         166,319 speakers), Ijo, Southeast (Latn, 2,471,000 speakers), Mfumte (Latn, 79,000 speakers), Dutch (Latn, 31,709,104 speakers). [code: soft-dotted]          

    Result: WARN

 >> com.google.fonts/check/article/images
    [EXPERIMENTAL CHECK - Since 2024/Mar/25]
    Validate size, and resolution of article images, and ensure article page has minimum length and includes visual assets.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    The purpose of this check is to ensure images (either raster or vector files) are not excessively large in filesize and resolution.                                
                                                                                                                                                                       
    These constraints are loosely based on infrastructure limitations under default configurations.                                                                    
                                                                                                                                                                       
    It also ensures that the article page has a minimum length and includes at least one visual asset.                                                                 
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/issues/4594

    WARN Family metadata at . does not have an article. [code: lacks-article]                                                                                          

    Result: WARN

 >> com.google.fonts/check/metadata/unreachable_subsetting
    Check for codepoints not covered by METADATA subsets.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    This check ensures that all encoded glyphs in the font are covered by a subset declared in the METADATA.pb. Google Fonts splits the font into a set of subset      
    fonts based on the contents of the `subsets` field and the subset definitions in the `glyphsets` repository.                                                       
                                                                                                                                                                       
    Any encoded glyphs which are not by any of these subset definitions will not be served in the subsetted fonts, and so will be unreachable to the end user.         
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/issues/4097
               https://github.com/fonttools/fontbakery/pull/4273

    WARN The following codepoints supported by the font are not covered by any subsets defined in the font's metadata file, and will never be served. You can solve    
         this by either manually adding additional subset declarations to METADATA.pb, or by editing the glyphset definitions.                                         
                                                                                                                                                                       
          • U+02C7 CARON: try adding one of: yi, tifinagh, canadian-aboriginal                                                                                         
          • U+02D8 BREVE: try adding one of: yi, canadian-aboriginal                                                                                                   
          • U+02D9 DOT ABOVE: try adding one of: yi, canadian-aboriginal                                                                                               
          • U+02DB OGONEK: try adding one of: yi, canadian-aboriginal                                                                                                  
          • U+02DD DOUBLE ACUTE ACCENT: not included in any glyphset definition                                                                                        
          • U+0302 COMBINING CIRCUMFLEX ACCENT: try adding one of: math, coptic, tifinagh, cherokee                                                                    
          • U+0306 COMBINING BREVE: try adding one of: tifinagh, old-permic                                                                                            
          • U+0307 COMBINING DOT ABOVE: try adding one of: syriac, tai-le, tifinagh, old-permic, canadian-aboriginal, coptic, malayalam, math                          
          • U+030A COMBINING RING ABOVE: try adding syriac                                                                                                             
          • U+030B COMBINING DOUBLE ACUTE ACCENT: try adding one of: osage, cherokee 14 more.                                                                          
                                                                                                                                                                       
         Use -F or --full-lists to disable shortening of long lists.                                                                                                   
                                                                                                                                                                       
         Or you can add the above codepoints to one of the subsets supported by the font: latin, latin-ext [code: unreachable-subsetting]                              

    Result: WARN

 >> com.google.fonts/check/glyphsets/shape_languages
    Shapes languages in all GF glyphsets.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    This check uses a heuristic to determine which GF glyphsets a font supports. Then it checks the font for correct shaping behaviour for all languages in those      
    glyphsets.                                                                                                                                                         
                                                                                                                                                                       
    More info: https://github.com/googlefonts/fontbakery/issues/4147

    FAIL GF_Latin_Core glyphset:                                                                                                                                       
                                                                                                                                                                       
                                                                                                                                                                       
           Language            FAIL messages                                                                                                                           
          ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━                                                                                                       
           ca_Latn (Catalan)   Some base glyphs were missing: ·                                                                                                        
           ^                   Shaper produced a .notdef                                                                                                               
                                                                                                                                                                       
                                                                                                                                                                       
         [code: failed-language-shaping]                                                                                                                               
    WARN GF_Latin_Core glyphset:                                                                                                                                       
                                                                                                                                                                       
                                                                                                                                                                       
           Language            WARN messages                                                                                                                           
          ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━                                                                                                  
           ca_Latn (Catalan)   Some auxiliary glyphs were missing: ·                                                                                                   
                                                                                                                                                                       
                                                                                                                                                                       
         [code: warning-language-shaping]                                                                                                                              
    FAIL GF_Latin_Core glyphset:                                                                                                                                       
                                                                                                                                                                       
                                                                                                                                                                       
           Language          FAIL messages                                                                                                                             
          ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━                                                                                                
           nl_Latn (Dutch)   Shaper didn't attach acutecomb to uni0237                                                                                                 
           ^                 Shaper didn't attach acutecomb to J                                                                                                       
                                                                                                                                                                       
                                                                                                                                                                       
         [code: failed-language-shaping]                                                                                                                               

# Result: FAIL

 >> com.google.fonts/check/name/license
    Check copyright namerecords match license file.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    A known licensing description must be provided in the NameID 14 (LICENSE DESCRIPTION) entries of the name table.                                                   
                                                                                                                                                                       
    The source of truth for this check (to determine which license is in use) is a file placed side-by-side to your font project including the licensing terms.        
                                                                                                                                                                       
    Depending on the chosen license, one of the following string snippets is expected to be found on the NameID 13 (LICENSE DESCRIPTION) entries of the name table:    
                                                                                                                                                                       
    - "This Font Software is licensed under the SIL Open Font License, Version 1.1. This license is available with a FAQ at: openfontlicense.org"                      
                                                                                                                                                                       
    - "Licensed under the Apache License, Version 2.0"                                                                                                                 
                                                                                                                                                                       
    - "Licensed under the Ubuntu Font Licence 1.0."                                                                                                                    
                                                                                                                                                                       
    Currently accepted licenses are Apache or Open Font License. For a small set of legacy families the Ubuntu Font License may be acceptable as well.                 
                                                                                                                                                                       
    When in doubt, please choose OFL for new font projects.                                                                                                            
                                                                                                                                                                       
    FAIL Font lacks NameID 13 (LICENSE DESCRIPTION). A proper licensing entry must be set. [code: missing]                                                             

# Result: FAIL

 >> com.google.fonts/check/fstype
    Checking OS/2 fsType does not impose restrictions.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    The fsType in the OS/2 table is a legacy DRM-related field. Fonts in the Google Fonts collection must have it set to zero (also known as "Installable              
    Embedding"). This setting indicates that the fonts can be embedded in documents and permanently installed by applications on remote systems.                       
                                                                                                                                                                       
    More detailed info is available at: https://docs.microsoft.com/en-us/typography/opentype/spec/os2#fstype                                                           
                                                                                                                                                                       
    FAIL In this font fsType is set to 8 meaning that: The font may be embedded but must only be installed temporarily on other systems.                               
                                                                                                                                                                       
         No such DRM restrictions can be enabled on the Google Fonts collection, so the fsType field must be set to zero (Installable Embedding) instead. [code: drm]  

# Result: FAIL

 >> com.google.fonts/check/gasp
    Is the Grid-fitting and Scan-conversion Procedure ('gasp') table set to optimize rendering?
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    Traditionally version 0 'gasp' tables were set so that font sizes below 8 ppem had no grid fitting but did have antialiasing. From 9-16 ppem, just grid fitting.   
    And fonts above 17ppem had both antialiasing and grid fitting toggled on. The use of accelerated graphics cards and higher resolution screens make this approach   
    obsolete. Microsoft's DirectWrite pushed this even further with much improved rendering built into the OS and apps.                                                
                                                                                                                                                                       
    In this scenario it makes sense to simply toggle all 4 flags ON for all font sizes.                                                                                
                                                                                                                                                                       
    FAIL Font is missing the 'gasp' table. Try exporting the font with autohinting enabled. If you are dealing with an unhinted font, it can be fixed by running the   
         fonts through the command 'gftools fix-nonhinting' GFTools is available at https://pypi.org/project/gftools/ [code: lacks-gasp]                               

# Result: FAIL

 >> com.google.fonts/check/glyph_coverage
    Check Google Fonts glyph coverage.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    Google Fonts expects that fonts in its collection support at least the minimal set of characters defined in the `GF-latin-core` glyph-set.                         
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/pull/2488

    FAIL Missing required codepoints:                                                                                                                                  
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x005E (CIRCUMFLEX ACCENT)                                                                                                                                 
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00A0 (NO-BREAK SPACE)                                                                                                                                    
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00A2 (CENT SIGN)                                                                                                                                         
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00A3 (POUND SIGN)                                                                                                                                        
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00A5 (YEN SIGN)                                                                                                                                          
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00A9 (COPYRIGHT SIGN)                                                                                                                                    
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00AA (FEMININE ORDINAL INDICATOR)                                                                                                                        
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00AE (REGISTERED SIGN)                                                                                                                                   
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00B6 (PILCROW SIGN)                                                                                                                                      
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00B7 (MIDDLE DOT)                                                                                                                                        
                                                                                                                                                                       
                                                                                                                                                                       
          - 4 more.                                                                                                                                                    
                                                                                                                                                                       
                                                                                                                                                                       
         Use -F or --full-lists to disable shortening of long lists. [code: missing-codepoints]                                                                        

# Result: FAIL

 >> com.google.fonts/check/meta/script_lang_tags
    Ensure fonts have ScriptLangTags declared on the 'meta' table.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    The OpenType 'meta' table originated at Apple. Microsoft added it to OT with just two DataMap records:                                                             
                                                                                                                                                                       
    - dlng: comma-separated ScriptLangTags that indicate which scripts, or languages and scripts, with possible variants, the font is designed for.                    
                                                                                                                                                                       
    - slng: comma-separated ScriptLangTags that indicate which scripts, or languages and scripts, with possible variants, the font supports.                           
                                                                                                                                                                       
    The slng structure is intended to describe which languages and scripts the font overall supports. For example, a Traditional Chinese font that also contains       
    Latin characters, can indicate Hant,Latn, showing that it supports Hant, the Traditional Chinese variant of the Hani script, and it also supports the Latn         
    script.                                                                                                                                                            
                                                                                                                                                                       
    The dlng structure is far more interesting. A font may contain various glyphs, but only a particular subset of the glyphs may be truly "leading" in the design,    
    while other glyphs may have been included for technical reasons. Such a Traditional Chinese font could only list Hant there, showing that it’s designed for        
    Traditional Chinese, but the font would omit Latn, because the developers don’t think the font is really recommended for purely Latin-script use.                  
                                                                                                                                                                       
    The tags used in the structures can comprise just script, or also language and script. For example, if a font has Bulgarian Cyrillic alternates in the locl        
    feature for the cyrl BGR OT languagesystem, it could also indicate in dlng explicitly that it supports bul-Cyrl. (Note that the scripts and languages in meta use  
    the ISO language and script codes, not the OpenType ones).                                                                                                         
                                                                                                                                                                       
    This check ensures that the font has the meta table containing the slng and dlng structures.                                                                       
                                                                                                                                                                       
    All families in the Google Fonts collection should contain the 'meta' table. Windows 10 already uses it when deciding on which fonts to fall back to. The Google   
    Fonts API and also other environments could use the data for smarter filtering. Most importantly, those entries should be added to the Noto fonts.                 
                                                                                                                                                                       
    In the font making process, some environments store this data in external files already. But the meta table provides a convenient way to store this inside the     
    font file, so some tools may add the data, and unrelated tools may read this data. This makes the solution much more portable and universal.                       
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/issues/3349

    WARN This font file does not have a 'meta' table. [code: lacks-meta-table]                                                                                         

    Result: WARN

 >> com.google.fonts/check/name/version_format
    Version format is correct in 'name' table?
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    For Google Fonts, the version string must be in the format "Version X.Y". The version number must be greater than or equal to 1.000. (Additional information       
    following the numeric version number is acceptable.)                                                                                                               
                                                                                                                                                                       
    FAIL The NameID.VERSION_STRING (nameID=5) value must follow the pattern "Version X.Y" with X.Y greater than or equal to 1.000. Current version string is:          
         "Version 0.007" [code: bad-version-strings]                                                                                                                   

# Result: FAIL

 >> com.google.fonts/check/smart_dropout
    Font enables smart dropout control in "prep" table instructions?
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    This setup is meant to ensure consistent rendering quality for fonts across all devices (with different rendering/hinting capabilities).                           
                                                                                                                                                                       
    Below is the snippet of instructions we expect to see in the fonts: B8 01 FF    PUSHW 0x01FF 85          SCANCTRL (unconditinally turn on dropout control mode)    
    B0 04       PUSHB 0x04 8D          SCANTYPE (enable smart dropout control)                                                                                         
                                                                                                                                                                       
    "Smart dropout control" means activating rules 1, 2 and 5: Rule 1: If a pixel's center falls within the glyph outline, that pixel is turned on. Rule 2: If a       
    contour falls exactly on a pixel's center, that pixel is turned on. Rule 5: If a scan line between two adjacent pixel centers (either vertical or horizontal) is   
    intersected by both an on-Transition contour and an off-Transition contour and neither of the pixels was already turned on by rules 1 and 2, turn on the pixel     
    which is closer to the midpoint between the on-Transition contour and off-Transition contour. This is "Smart" dropout control.                                     
                                                                                                                                                                       
    For more detailed info (such as other rules not enabled in this snippet), please refer to the TrueType Instruction Set documentation.                              
                                                                                                                                                                       
    Generally this occurs with unhinted fonts; if you are not using autohinting, use gftools-fix-nonhinting (or just gftools-fix-font) to fix this issue.              
                                                                                                                                                                       
    FAIL The 'prep' table does not contain TrueType instructions enabling smart dropout control. To fix, export the font with autohinting enabled, or run ttfautohint  
         on the font, or run the gftools fix-nonhinting script. [code: lacks-smart-dropout]                                                                            

# Result: FAIL

 >> com.google.fonts/check/stylisticset_description
    Ensure Stylistic Sets have description.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    Stylistic sets should provide description text. Programs such as InDesign, TextEdit and Inkscape use that info to display to the users so that they know what a    
    given stylistic set offers.                                                                                                                                        
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/issues/3155

    WARN The stylistic set ss01 lacks a description string on the 'name' table. [code: missing-description]                                                            
    WARN The stylistic set ss02 lacks a description string on the 'name' table. [code: missing-description]                                                            
    WARN The stylistic set ss03 lacks a description string on the 'name' table. [code: missing-description]                                                            

    Result: WARN

 >> com.google.fonts/check/vendor_id
    Checking OS/2 achVendID.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    Microsoft keeps a list of font vendors and their respective contact info. This list is updated regularly and is indexed by a 4-char "Vendor ID" which is stored    
    in the achVendID field of the OS/2 table.                                                                                                                          
                                                                                                                                                                       
    Registering your ID is not mandatory, but it is a good practice since some applications may display the type designer / type foundry contact info on some dialog   
    and also because that info will be visible on Microsoft's website:                                                                                                 
                                                                                                                                                                       
    https://docs.microsoft.com/en-us/typography/vendors/                                                                                                               
                                                                                                                                                                       
    This check verifies whether or not a given font's vendor ID is registered in that list or if it has some of the default values used by the most common font        
    editors.                                                                                                                                                           
                                                                                                                                                                       
    Each new FontBakery release includes a cached copy of that list of vendor IDs. If you registered recently, you're safe to ignore warnings emitted by this check,   
    since your ID will soon be included in one of our upcoming releases.                                                                                               
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/issues/3943

    WARN OS/2 VendorID value 'NONE' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it  
         to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx [code: unknown]             

    Result: WARN

 >> com.google.fonts/check/vertical_metrics
    Check font follows the Google Fonts vertical metric schema
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    This check generally enforces Google Fonts’ vertical metrics specifications. In particular: * lineGap must be 0 * Sum of hhea ascender + abs(descender) + linegap  
    must be between 120% and 200% of UPM * Warning if sum is over 150% of UPM                                                                                          
                                                                                                                                                                       
    The threshold levels 150% (WARN) and 200% (FAIL) are somewhat arbitrarily chosen and may hint at a glaring mistake in the metrics calculations or UPM settings.    
                                                                                                                                                                       
    Our documentation includes further information: https://github.com/googlefonts/gf-docs/tree/main/VerticalMetrics                                                   
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/pull/3762
               https://github.com/fonttools/fontbakery/pull/3921

    FAIL OS/2.sTypoLineGap is "100" it should be 0 [code: bad-OS/2.sTypoLineGap]                                                                                       
    FAIL hhea.lineGap is "100" it should be 0 [code: bad-hhea.lineGap]                                                                                                 

#  Result: FAIL


Total:
    ERROR: 0
    FATAL: 0
    FAIL: 12
    WARN: 12
    INFO: 8
    SKIP: 120
    PASS: 96

`