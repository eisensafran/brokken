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

 >> com.google.fonts/check/outline_jaggy_segments
    Do outlines contain any jaggy segments?
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    This check heuristically detects outline segments which form a particularly small angle, indicative of an outline error. This may cause false positives in cases   
    such as extreme ink traps, so should be regarded as advisory and backed up by manual inspection.                                                                   
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/issues/3064

    WARN The following glyphs have jaggy segments:                                                                                                                     
                                                                                                                                                                       
                                                                                                                                                                       
          * T_T: L<<370.0,1.0>--<252.0,0.0>>/L<<252.0,0.0>--<252.0,0.0>> = 0.48554583000816465 [code: found-jaggy-segments]                                            
                                                                                                                                                                       

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
                                                                                                                                                                       
          * Agrave (U+00C0): L<<386.0,217.0>--<232.0,218.0>>                                                                                                           
                                                                                                                                                                       
          * Agrave.ss02: L<<662.0,261.0>--<661.0,127.0>>                                                                                                               
                                                                                                                                                                       
          * Amacron (U+0100): L<<386.0,217.0>--<232.0,218.0>>                                                                                                          
                                                                                                                                                                       
          * Amacron.ss02: L<<662.0,261.0>--<661.0,127.0>>                                                                                                              
                                                                                                                                                                       
          * Aogonek (U+0104): L<<386.0,217.0>--<232.0,218.0>>                                                                                                          
                                                                                                                                                                       
          * Aogonek.ss02: L<<662.0,261.0>--<661.0,127.0>>                                                                                                              
                                                                                                                                                                       
          * Aring (U+00C5): L<<386.0,217.0>--<232.0,218.0>>                                                                                                            
                                                                                                                                                                       
          * Aring.ss02: L<<662.0,261.0>--<661.0,127.0>>                                                                                                                
                                                                                                                                                                       
          * Atilde (U+00C3): L<<386.0,217.0>--<232.0,218.0>>                                                                                                           
                                                                                                                                                                       
          * Atilde.ss02: L<<662.0,261.0>--<661.0,127.0>>                                                                                                               
                                                                                                                                                                       
          * B (U+0042): L<<485.0,-1.0>--<144.0,0.0>>                                                                                                                   
                                                                                                                                                                       
          * C (U+0043): L<<20.0,209.0>--<22.0,499.0>>                                                                                                                  
                                                                                                                                                                       
          * C (U+0043): L<<531.0,1.0>--<352.0,0.0>>                                                                                                                    
                                                                                                                                                                       
          * Cacute (U+0106): L<<20.0,209.0>--<22.0,499.0>>                                                                                                             
                                                                                                                                                                       
          * Cacute (U+0106): L<<531.0,1.0>--<352.0,0.0>>                                                                                                               
                                                                                                                                                                       
          * Ccaron (U+010C): L<<20.0,209.0>--<22.0,499.0>>                                                                                                             
                                                                                                                                                                       
          * Ccaron (U+010C): L<<531.0,1.0>--<352.0,0.0>>                                                                                                               
                                                                                                                                                                       
          * Ccedilla (U+00C7): L<<20.0,209.0>--<22.0,499.0>>                                                                                                           
                                                                                                                                                                       
          * Ccedilla (U+00C7): L<<531.0,1.0>--<359.0,0.0>>                                                                                                             
                                                                                                                                                                       
          * Ccircumflex (U+0108): L<<20.0,209.0>--<22.0,499.0>>                                                                                                        
                                                                                                                                                                       
          * Ccircumflex (U+0108): L<<531.0,1.0>--<352.0,0.0>>                                                                                                          
                                                                                                                                                                       
          * Cdotaccent (U+010A): L<<20.0,209.0>--<22.0,499.0>>                                                                                                         
                                                                                                                                                                       
          * Cdotaccent (U+010A): L<<531.0,1.0>--<352.0,0.0>>                                                                                                           
                                                                                                                                                                       
          * G (U+0047): L<<20.0,209.0>--<22.0,499.0>>                                                                                                                  
                                                                                                                                                                       
          * G.ss01: L<<20.0,84.0>--<23.0,622.0>>                                                                                                                       
                                                                                                                                                                       
          * Gbreve (U+011E): L<<20.0,209.0>--<22.0,499.0>>                                                                                                             
                                                                                                                                                                       
          * Gcircumflex (U+011C): L<<20.0,209.0>--<22.0,499.0>>                                                                                                        
                                                                                                                                                                       
          * Gdotaccent (U+0120): L<<20.0,209.0>--<22.0,499.0>>                                                                                                         
                                                                                                                                                                       
          * H (U+0048): L<<605.0,1.0>--<468.0,0.0>>                                                                                                                    
                                                                                                                                                                       
          * Hcircumflex (U+0124): L<<605.0,1.0>--<468.0,0.0>>                                                                                                          
                                                                                                                                                                       
          * I (U+0049): L<<250.0,488.0>--<249.0,127.0>>                                                                                                                
                                                                                                                                                                       
          * I (U+0049): L<<91.0,164.0>--<92.0,565.0>>                                                                                                                  
                                                                                                                                                                       
          * IJ (U+0132): L<<250.0,488.0>--<249.0,127.0>>                                                                                                               
                                                                                                                                                                       
          * IJ (U+0132): L<<91.0,164.0>--<92.0,565.0>>                                                                                                                 
                                                                                                                                                                       
          * Iacute (U+00CD): L<<250.0,488.0>--<249.0,127.0>>                                                                                                           
                                                                                                                                                                       
          * Iacute (U+00CD): L<<91.0,164.0>--<92.0,565.0>>                                                                                                             
                                                                                                                                                                       
          * Icircumflex (U+00CE): L<<250.0,488.0>--<249.0,127.0>>                                                                                                      
                                                                                                                                                                       
          * Icircumflex (U+00CE): L<<91.0,164.0>--<92.0,565.0>>                                                                                                        
                                                                                                                                                                       
          * Idieresis (U+00CF): L<<250.0,488.0>--<249.0,127.0>>                                                                                                        
                                                                                                                                                                       
          * Idieresis (U+00CF): L<<91.0,164.0>--<92.0,565.0>>                                                                                                          
                                                                                                                                                                       
          * Idotaccent (U+0130): L<<250.0,488.0>--<249.0,127.0>>                                                                                                       
                                                                                                                                                                       
          * Idotaccent (U+0130): L<<91.0,164.0>--<92.0,565.0>>                                                                                                         
                                                                                                                                                                       
          * Igrave (U+00CC): L<<250.0,488.0>--<249.0,127.0>>                                                                                                           
                                                                                                                                                                       
          * Igrave (U+00CC): L<<91.0,164.0>--<92.0,565.0>>                                                                                                             
                                                                                                                                                                       
          * Imacron (U+012A): L<<250.0,488.0>--<249.0,127.0>>                                                                                                          
                                                                                                                                                                       
          * Imacron (U+012A): L<<91.0,164.0>--<92.0,565.0>>                                                                                                            
                                                                                                                                                                       
          * Iogonek (U+012E): L<<250.0,488.0>--<249.0,127.0>>                                                                                                          
                                                                                                                                                                       
          * Iogonek (U+012E): L<<91.0,164.0>--<92.0,565.0>>                                                                                                            
                                                                                                                                                                       
          * Itilde (U+0129): L<<250.0,488.0>--<249.0,127.0>>                                                                                                           
                                                                                                                                                                       
          * Itilde (U+0129): L<<91.0,164.0>--<92.0,565.0>>                                                                                                             
                                                                                                                                                                       
          * L (U+004C): L<<238.0,518.0>--<237.0,168.0>>                                                                                                                
                                                                                                                                                                       
          * Lacute (U+0139): L<<238.0,518.0>--<237.0,168.0>>                                                                                                           
                                                                                                                                                                       
          * Lcaron (U+013D): L<<238.0,518.0>--<237.0,168.0>>                                                                                                           
                                                                                                                                                                       
          * N (U+004E): L<<662.0,501.0>--<664.0,0.0>>                                                                                                                  
                                                                                                                                                                       
          * Nacute (U+0143): L<<662.0,501.0>--<664.0,0.0>>                                                                                                             
                                                                                                                                                                       
          * Ncaron (U+0147): L<<662.0,501.0>--<664.0,0.0>>                                                                                                             
                                                                                                                                                                       
          * Ntilde (U+00D1): L<<662.0,501.0>--<664.0,0.0>>                                                                                                             
                                                                                                                                                                       
          * O (U+004F): L<<157.0,133.0>--<372.0,132.0>>                                                                                                                
                                                                                                                                                                       
          * O (U+004F): L<<419.0,0.0>--<129.0,-1.0>>                                                                                                                   
                                                                                                                                                                       
          * OE (U+0152): L<<157.0,133.0>--<372.0,132.0>>                                                                                                               
                                                                                                                                                                       
          * OE (U+0152): L<<419.0,0.0>--<129.0,-1.0>>                                                                                                                  
                                                                                                                                                                       
          * OE (U+0152): L<<619.0,700.0>--<885.0,702.0>>                                                                                                               
                                                                                                                                                                       
          * Oacute (U+00D3): L<<157.0,133.0>--<372.0,132.0>>                                                                                                           
                                                                                                                                                                       
          * Oacute (U+00D3): L<<419.0,0.0>--<129.0,-1.0>>                                                                                                              
                                                                                                                                                                       
          * Ocircumflex (U+00D4): L<<157.0,133.0>--<372.0,132.0>>                                                                                                      
                                                                                                                                                                       
          * Ocircumflex (U+00D4): L<<419.0,0.0>--<129.0,-1.0>>                                                                                                         
                                                                                                                                                                       
          * Odieresis (U+00D6): L<<157.0,133.0>--<372.0,132.0>>                                                                                                        
                                                                                                                                                                       
          * Odieresis (U+00D6): L<<419.0,0.0>--<129.0,-1.0>>                                                                                                           
                                                                                                                                                                       
          * Ograve (U+00D2): L<<157.0,133.0>--<372.0,132.0>>                                                                                                           
                                                                                                                                                                       
          * Ograve (U+00D2): L<<419.0,0.0>--<129.0,-1.0>>                                                                                                              
                                                                                                                                                                       
          * Ohungarumlaut (U+0150): L<<157.0,133.0>--<372.0,132.0>>                                                                                                    
                                                                                                                                                                       
          * Ohungarumlaut (U+0150): L<<419.0,0.0>--<129.0,-1.0>>                                                                                                       
                                                                                                                                                                       
          * Omacron (U+014C): L<<157.0,133.0>--<372.0,132.0>>                                                                                                          
                                                                                                                                                                       
          * Omacron (U+014C): L<<419.0,0.0>--<129.0,-1.0>>                                                                                                             
                                                                                                                                                                       
          * Oslash (U+00D8): L<<419.0,0.0>--<214.0,-1.0>>                                                                                                              
                                                                                                                                                                       
          * Otilde (U+00D5): L<<157.0,133.0>--<372.0,132.0>>                                                                                                           
                                                                                                                                                                       
          * Otilde (U+00D5): L<<419.0,0.0>--<129.0,-1.0>>                                                                                                              
                                                                                                                                                                       
          * P (U+0050): L<<103.0,198.0>--<102.0,546.0>>                                                                                                                
                                                                                                                                                                       
          * Q (U+0051): L<<307.0,700.0>--<518.0,699.0>>                                                                                                                
                                                                                                                                                                       
          * R (U+0052): L<<326.0,698.0>--<563.0,700.0>>                                                                                                                
                                                                                                                                                                       
          * Racute (U+0154): L<<326.0,698.0>--<563.0,700.0>>                                                                                                           
                                                                                                                                                                       
          * Rcaron (U+0158): L<<326.0,698.0>--<563.0,700.0>>                                                                                                           
                                                                                                                                                                       
          * S (U+0053): L<<193.0,698.0>--<454.0,700.0>>                                                                                                                
                                                                                                                                                                       
          * S (U+0053): L<<446.0,0.0>--<55.0,1.0>>                                                                                                                     
                                                                                                                                                                       
          * S (U+0053): L<<55.0,1.0>--<56.0,129.0>>                                                                                                                    
                                                                                                                                                                       
          * Sacute (U+015A): L<<193.0,698.0>--<454.0,700.0>>                                                                                                           
                                                                                                                                                                       
          * Sacute (U+015A): L<<446.0,0.0>--<55.0,1.0>>                                                                                                                
                                                                                                                                                                       
          * Sacute (U+015A): L<<55.0,1.0>--<56.0,129.0>>                                                                                                               
                                                                                                                                                                       
          * Scaron (U+0160): L<<193.0,698.0>--<454.0,700.0>>                                                                                                           
                                                                                                                                                                       
          * Scaron (U+0160): L<<446.0,0.0>--<55.0,1.0>>                                                                                                                
                                                                                                                                                                       
          * Scaron (U+0160): L<<55.0,1.0>--<56.0,129.0>>                                                                                                               
                                                                                                                                                                       
          * Scedilla (U+015E): L<<193.0,698.0>--<454.0,700.0>>                                                                                                         
                                                                                                                                                                       
          * Scedilla (U+015E): L<<55.0,1.0>--<56.0,129.0>>                                                                                                             
                                                                                                                                                                       
          * Scircumflex (U+015C): L<<193.0,698.0>--<454.0,700.0>>                                                                                                      
                                                                                                                                                                       
          * Scircumflex (U+015C): L<<446.0,0.0>--<55.0,1.0>>                                                                                                           
                                                                                                                                                                       
          * Scircumflex (U+015C): L<<55.0,1.0>--<56.0,129.0>>                                                                                                          
                                                                                                                                                                       
          * T_T: L<<370.0,1.0>--<252.0,0.0>>                                                                                                                           
                                                                                                                                                                       
          * T_T: L<<842.0,-1.0>--<688.0,0.0>>                                                                                                                          
                                                                                                                                                                       
          * Thorn (U+00DE): L<<108.0,704.0>--<296.0,703.0>>                                                                                                            
                                                                                                                                                                       
          * Thorn (U+00DE): L<<256.0,425.0>--<257.0,262.0>>                                                                                                            
                                                                                                                                                                       
          * Thorn (U+00DE): L<<91.0,164.0>--<92.0,565.0>>                                                                                                              
                                                                                                                                                                       
          * ae (U+00E6): L<<775.0,1.0>--<549.0,0.0>>                                                                                                                   
                                                                                                                                                                       
          * aeacute (U+01FD): L<<775.0,1.0>--<549.0,0.0>>                                                                                                              
                                                                                                                                                                       
          * ampersand (U+0026): L<<168.0,702.0>--<417.0,700.0>>                                                                                                        
                                                                                                                                                                       
          * bar (U+007C): L<<222.0,660.0>--<218.0,-175.0>>                                                                                                             
                                                                                                                                                                       
          * bar (U+007C): L<<80.0,-108.0>--<86.0,654.0>>                                                                                                               
                                                                                                                                                                       
          * bracketleft (U+005B): L<<319.0,-129.0>--<82.0,-130.0>>                                                                                                     
                                                                                                                                                                       
          * bracketleft (U+005B): L<<82.0,-130.0>--<81.0,866.0>>                                                                                                       
                                                                                                                                                                       
          * bracketright (U+005D): L<<268.0,-130.0>--<31.0,-129.0>>                                                                                                    
                                                                                                                                                                       
          * bracketright (U+005D): L<<269.0,866.0>--<268.0,-130.0>>                                                                                                    
                                                                                                                                                                       
          * c (U+0063): L<<457.0,1.0>--<278.0,0.0>>                                                                                                                    
                                                                                                                                                                       
          * c (U+0063): L<<481.0,493.0>--<482.0,330.0>>                                                                                                                
                                                                                                                                                                       
          * cacute (U+0107): L<<457.0,1.0>--<278.0,0.0>>                                                                                                               
                                                                                                                                                                       
          * cacute (U+0107): L<<481.0,493.0>--<482.0,330.0>>                                                                                                           
                                                                                                                                                                       
          * ccaron (U+010D): L<<457.0,1.0>--<278.0,0.0>>                                                                                                               
                                                                                                                                                                       
          * ccaron (U+010D): L<<481.0,493.0>--<482.0,330.0>>                                                                                                           
                                                                                                                                                                       
          * ccedilla (U+00E7): L<<481.0,493.0>--<482.0,330.0>>                                                                                                         
                                                                                                                                                                       
          * ccircumflex (U+0109): L<<457.0,1.0>--<278.0,0.0>>                                                                                                          
                                                                                                                                                                       
          * ccircumflex (U+0109): L<<481.0,493.0>--<482.0,330.0>>                                                                                                      
                                                                                                                                                                       
          * cdotaccent (U+010B): L<<457.0,1.0>--<278.0,0.0>>                                                                                                           
                                                                                                                                                                       
          * cdotaccent (U+010B): L<<481.0,493.0>--<482.0,330.0>>                                                                                                       
                                                                                                                                                                       
          * d (U+0064): L<<320.0,196.0>--<319.0,399.0>>                                                                                                                
                                                                                                                                                                       
          * dcaron (U+010F): L<<320.0,196.0>--<319.0,399.0>>                                                                                                           
                                                                                                                                                                       
          * dcroat (U+0111): L<<320.0,196.0>--<319.0,399.0>>                                                                                                           
                                                                                                                                                                       
          * dollar (U+0024): L<<341.0,590.0>--<211.0,589.0>>                                                                                                           
                                                                                                                                                                       
          * dotlessi (U+0131): L<<228.0,326.0>--<229.0,154.0>>                                                                                                         
                                                                                                                                                                       
          * e (U+0065): L<<487.0,1.0>--<261.0,0.0>>                                                                                                                    
                                                                                                                                                                       
          * eacute (U+00E9): L<<487.0,1.0>--<261.0,0.0>>                                                                                                               
                                                                                                                                                                       
          * ecaron (U+011B): L<<487.0,1.0>--<261.0,0.0>>                                                                                                               
                                                                                                                                                                       
          * ecircumflex (U+00EA): L<<487.0,1.0>--<261.0,0.0>>                                                                                                          
                                                                                                                                                                       
          * edieresis (U+00EB): L<<487.0,1.0>--<261.0,0.0>>                                                                                                            
                                                                                                                                                                       
          * edotaccent (U+0117): L<<487.0,1.0>--<261.0,0.0>>                                                                                                           
                                                                                                                                                                       
          * egrave (U+00E8): L<<487.0,1.0>--<261.0,0.0>>                                                                                                               
                                                                                                                                                                       
          * eight (U+0038): L<<185.0,569.0>--<184.0,452.0>>                                                                                                            
                                                                                                                                                                       
          * eight (U+0038): L<<445.0,0.0>--<112.0,1.0>>                                                                                                                
                                                                                                                                                                       
          * emacron (U+0113): L<<487.0,1.0>--<261.0,0.0>>                                                                                                              
                                                                                                                                                                       
          * emdash (U+2014): L<<826.0,193.0>--<140.0,188.0>>                                                                                                           
                                                                                                                                                                       
          * eogonek (U+0119): L<<487.0,1.0>--<347.0,0.0>>                                                                                                              
                                                                                                                                                                       
          * g (U+0067): L<<457.0,-236.0>--<142.0,-238.0>>                                                                                                              
                                                                                                                                                                       
          * gbreve (U+011F): L<<457.0,-236.0>--<142.0,-238.0>>                                                                                                         
                                                                                                                                                                       
          * gcircumflex (U+011D): L<<457.0,-236.0>--<142.0,-238.0>>                                                                                                    
                                                                                                                                                                       
          * gdotaccent (U+0121): L<<457.0,-236.0>--<142.0,-238.0>>                                                                                                     
                                                                                                                                                                       
          * germandbls (U+00DF): L<<71.0,105.0>--<69.0,365.0>>                                                                                                         
                                                                                                                                                                       
          * h (U+0068): L<<226.0,382.0>--<225.0,124.0>>                                                                                                                
                                                                                                                                                                       
          * hbar (U+0127): L<<280.0,1.0>--<62.0,0.0>>                                                                                                                  
                                                                                                                                                                       
          * hcircumflex (U+0125): L<<226.0,382.0>--<225.0,124.0>>                                                                                                      
                                                                                                                                                                       
          * i (U+0069): L<<272.0,1.0>--<66.0,0.0>>                                                                                                                     
                                                                                                                                                                       
          * i.loclTRK: L<<228.0,326.0>--<229.0,154.0>>                                                                                                                 
                                                                                                                                                                       
          * iacute (U+00ED): L<<228.0,326.0>--<229.0,154.0>>                                                                                                           
                                                                                                                                                                       
          * icircumflex (U+00EE): L<<228.0,326.0>--<229.0,154.0>>                                                                                                      
                                                                                                                                                                       
          * idieresis (U+00EF): L<<228.0,326.0>--<229.0,154.0>>                                                                                                        
                                                                                                                                                                       
          * igrave (U+00EC): L<<228.0,326.0>--<229.0,154.0>>                                                                                                           
                                                                                                                                                                       
          * ij (U+0133): L<<272.0,1.0>--<66.0,0.0>>                                                                                                                    
                                                                                                                                                                       
          * imacron (U+012B): L<<228.0,326.0>--<229.0,154.0>>                                                                                                          
                                                                                                                                                                       
          * iogonek (U+012F): L<<228.0,326.0>--<229.0,154.0>>                                                                                                          
                                                                                                                                                                       
          * k (U+006B): L<<277.0,1.0>--<58.0,0.0>>                                                                                                                     
                                                                                                                                                                       
          * l (U+006C): L<<56.0,82.0>--<52.0,590.0>>                                                                                                                   
                                                                                                                                                                       
          * lacute (U+013A): L<<56.0,82.0>--<52.0,590.0>>                                                                                                              
                                                                                                                                                                       
          * lcaron (U+013E): L<<56.0,82.0>--<52.0,590.0>>                                                                                                              
                                                                                                                                                                       
          * lslash (U+0142): L<<56.0,416.0>--<55.0,590.0>>                                                                                                             
                                                                                                                                                                       
          * m (U+006D): L<<75.0,142.0>--<74.0,356.0>>                                                                                                                  
                                                                                                                                                                       
          * nine (U+0039): L<<333.0,448.0>--<334.0,568.0>>                                                                                                             
                                                                                                                                                                       
          * o (U+006F): L<<330.0,152.0>--<329.0,413.0>>                                                                                                                
                                                                                                                                                                       
          * o (U+006F): L<<352.0,0.0>--<131.0,-1.0>>                                                                                                                   
                                                                                                                                                                       
          * oacute (U+00F3): L<<330.0,152.0>--<329.0,413.0>>                                                                                                           
                                                                                                                                                                       
          * oacute (U+00F3): L<<352.0,0.0>--<131.0,-1.0>>                                                                                                              
                                                                                                                                                                       
          * ocircumflex (U+00F4): L<<330.0,152.0>--<329.0,413.0>>                                                                                                      
                                                                                                                                                                       
          * ocircumflex (U+00F4): L<<352.0,0.0>--<131.0,-1.0>>                                                                                                         
                                                                                                                                                                       
          * odieresis (U+00F6): L<<330.0,152.0>--<329.0,413.0>>                                                                                                        
                                                                                                                                                                       
          * odieresis (U+00F6): L<<352.0,0.0>--<131.0,-1.0>>                                                                                                           
                                                                                                                                                                       
          * oe (U+0153): L<<307.0,0.0>--<131.0,-1.0>>                                                                                                                  
                                                                                                                                                                       
          * oe (U+0153): L<<752.0,1.0>--<526.0,0.0>>                                                                                                                   
                                                                                                                                                                       
          * ograve (U+00F2): L<<330.0,152.0>--<329.0,413.0>>                                                                                                           
                                                                                                                                                                       
          * ograve (U+00F2): L<<352.0,0.0>--<131.0,-1.0>>                                                                                                              
                                                                                                                                                                       
          * ohungarumlaut (U+0151): L<<330.0,152.0>--<329.0,413.0>>                                                                                                    
                                                                                                                                                                       
          * ohungarumlaut (U+0151): L<<352.0,0.0>--<131.0,-1.0>>                                                                                                       
                                                                                                                                                                       
          * omacron (U+014D): L<<330.0,152.0>--<329.0,413.0>>                                                                                                          
                                                                                                                                                                       
          * omacron (U+014D): L<<352.0,0.0>--<131.0,-1.0>>                                                                                                             
                                                                                                                                                                       
          * one (U+0031): L<<106.0,141.0>--<103.0,529.0>>                                                                                                              
                                                                                                                                                                       
          * one (U+0031): L<<222.0,1.0>--<76.0,2.0>>                                                                                                                   
                                                                                                                                                                       
          * oslash (U+00F8): L<<330.0,152.0>--<329.0,324.0>>                                                                                                           
                                                                                                                                                                       
          * oslash (U+00F8): L<<352.0,0.0>--<155.0,-1.0>>                                                                                                              
                                                                                                                                                                       
          * otilde (U+00F5): L<<330.0,152.0>--<329.0,413.0>>                                                                                                           
                                                                                                                                                                       
          * otilde (U+00F5): L<<352.0,0.0>--<131.0,-1.0>>                                                                                                              
                                                                                                                                                                       
          * quotedbl (U+0022): L<<306.0,705.0>--<307.0,581.0>>                                                                                                         
                                                                                                                                                                       
          * s (U+0073): L<<35.0,1.0>--<36.0,128.0>>                                                                                                                    
                                                                                                                                                                       
          * s.ss01: L<<23.0,204.0>--<22.0,482.0>>                                                                                                                      
                                                                                                                                                                       
          * s.ss01: L<<320.0,0.0>--<90.0,2.0>>                                                                                                                         
                                                                                                                                                                       
          * sacute (U+015B): L<<35.0,1.0>--<36.0,128.0>>                                                                                                               
                                                                                                                                                                       
          * scaron (U+0161): L<<35.0,1.0>--<36.0,128.0>>                                                                                                               
                                                                                                                                                                       
          * scedilla (U+015F): L<<35.0,1.0>--<36.0,128.0>>                                                                                                             
                                                                                                                                                                       
          * scircumflex (U+015D): L<<35.0,1.0>--<36.0,128.0>>                                                                                                          
                                                                                                                                                                       
          * seven (U+0037): L<<280.0,1.0>--<130.0,0.0>>                                                                                                                
                                                                                                                                                                       
          * six (U+0036): L<<186.0,294.0>--<185.0,102.0>>                                                                                                              
                                                                                                                                                                       
          * six (U+0036): L<<188.0,550.0>--<187.0,379.0>>                                                                                                              
                                                                                                                                                                       
          * three (U+0033): L<<339.0,67.0>--<337.0,301.0>>                                                                                                             
                                                                                                                                                                       
          * two (U+0032): L<<449.0,2.0>--<37.0,0.0>>                                                                                                                   
                                                                                                                                                                       
          * u (U+0075): L<<314.0,154.0>--<315.0,362.0>>                                                                                                                
                                                                                                                                                                       
          * u (U+0075): L<<486.0,377.0>--<485.0,124.0>>                                                                                                                
                                                                                                                                                                       
          * u (U+0075): L<<71.0,520.0>--<207.0,521.0>>                                                                                                                 
                                                                                                                                                                       
          * uacute (U+00FA): L<<314.0,154.0>--<315.0,362.0>>                                                                                                           
                                                                                                                                                                       
          * uacute (U+00FA): L<<486.0,377.0>--<485.0,124.0>>                                                                                                           
                                                                                                                                                                       
          * uacute (U+00FA): L<<71.0,520.0>--<207.0,521.0>>                                                                                                            
                                                                                                                                                                       
          * ubreve (U+016D): L<<314.0,154.0>--<315.0,362.0>>                                                                                                           
                                                                                                                                                                       
          * ubreve (U+016D): L<<486.0,377.0>--<485.0,124.0>>                                                                                                           
                                                                                                                                                                       
          * ubreve (U+016D): L<<71.0,520.0>--<207.0,521.0>>                                                                                                            
                                                                                                                                                                       
          * ucircumflex (U+00FB): L<<314.0,154.0>--<315.0,362.0>>                                                                                                      
                                                                                                                                                                       
          * ucircumflex (U+00FB): L<<486.0,377.0>--<485.0,124.0>>                                                                                                      
                                                                                                                                                                       
          * ucircumflex (U+00FB): L<<71.0,520.0>--<207.0,521.0>>                                                                                                       
                                                                                                                                                                       
          * udieresis (U+00FC): L<<314.0,154.0>--<315.0,362.0>>                                                                                                        
                                                                                                                                                                       
          * udieresis (U+00FC): L<<486.0,377.0>--<485.0,124.0>>                                                                                                        
                                                                                                                                                                       
          * udieresis (U+00FC): L<<71.0,520.0>--<207.0,521.0>>                                                                                                         
                                                                                                                                                                       
          * ugrave (U+00F9): L<<314.0,154.0>--<315.0,362.0>>                                                                                                           
                                                                                                                                                                       
          * ugrave (U+00F9): L<<486.0,377.0>--<485.0,124.0>>                                                                                                           
                                                                                                                                                                       
          * ugrave (U+00F9): L<<71.0,520.0>--<207.0,521.0>>                                                                                                            
                                                                                                                                                                       
          * uhungarumlaut (U+0171): L<<314.0,154.0>--<315.0,362.0>>                                                                                                    
                                                                                                                                                                       
          * uhungarumlaut (U+0171): L<<486.0,377.0>--<485.0,124.0>>                                                                                                    
                                                                                                                                                                       
          * uhungarumlaut (U+0171): L<<71.0,520.0>--<207.0,521.0>>                                                                                                     
                                                                                                                                                                       
          * umacron (U+016B): L<<314.0,154.0>--<315.0,362.0>>                                                                                                          
                                                                                                                                                                       
          * umacron (U+016B): L<<486.0,377.0>--<485.0,124.0>>                                                                                                          
                                                                                                                                                                       
          * umacron (U+016B): L<<71.0,520.0>--<207.0,521.0>>                                                                                                           
                                                                                                                                                                       
          * uni0122 (U+0122): L<<20.0,209.0>--<22.0,499.0>>                                                                                                            
                                                                                                                                                                       
          * uni0123 (U+0123): L<<457.0,-236.0>--<142.0,-238.0>>                                                                                                        
                                                                                                                                                                       
          * uni0137 (U+0137): L<<277.0,1.0>--<58.0,0.0>>                                                                                                               
                                                                                                                                                                       
          * uni013B (U+013B): L<<238.0,518.0>--<237.0,168.0>>                                                                                                          
                                                                                                                                                                       
          * uni013C (U+013C): L<<56.0,82.0>--<52.0,590.0>>                                                                                                             
                                                                                                                                                                       
          * uni0145 (U+0145): L<<662.0,501.0>--<664.0,0.0>>                                                                                                            
                                                                                                                                                                       
          * uni0156 (U+0156): L<<326.0,698.0>--<563.0,700.0>>                                                                                                          
                                                                                                                                                                       
          * uni01F4 (U+01F4): L<<20.0,209.0>--<22.0,499.0>>                                                                                                            
                                                                                                                                                                       
          * uni01F5 (U+01F5): L<<457.0,-236.0>--<142.0,-238.0>>                                                                                                        
                                                                                                                                                                       
          * uni0218 (U+0218): L<<193.0,698.0>--<454.0,700.0>>                                                                                                          
                                                                                                                                                                       
          * uni0218 (U+0218): L<<446.0,0.0>--<55.0,1.0>>                                                                                                               
                                                                                                                                                                       
          * uni0218 (U+0218): L<<55.0,1.0>--<56.0,129.0>>                                                                                                              
                                                                                                                                                                       
          * uni0219 (U+0219): L<<35.0,1.0>--<36.0,128.0>>                                                                                                              
                                                                                                                                                                       
          * uni1E20 (U+1E20): L<<20.0,209.0>--<22.0,499.0>>                                                                                                            
                                                                                                                                                                       
          * uni1E21 (U+1E21): L<<457.0,-236.0>--<142.0,-238.0>>                                                                                                        
                                                                                                                                                                       
          * uni1E9E (U+1E9E): L<<110.0,481.0>--<109.0,609.0>>                                                                                                          
                                                                                                                                                                       
          * uni1E9E (U+1E9E): L<<113.0,105.0>--<111.0,345.0>>                                                                                                          
                                                                                                                                                                       
          * uni1EBD (U+1EBD): L<<487.0,1.0>--<261.0,0.0>>                                                                                                              
                                                                                                                                                                       
          * uogonek (U+0173): L<<314.0,154.0>--<315.0,362.0>>                                                                                                          
                                                                                                                                                                       
          * uogonek (U+0173): L<<486.0,377.0>--<485.0,124.0>>                                                                                                          
                                                                                                                                                                       
          * uogonek (U+0173): L<<71.0,520.0>--<207.0,521.0>>                                                                                                           
                                                                                                                                                                       
          * uring (U+016F): L<<314.0,154.0>--<315.0,362.0>>                                                                                                            
                                                                                                                                                                       
          * uring (U+016F): L<<486.0,377.0>--<485.0,124.0>>                                                                                                            
                                                                                                                                                                       
          * uring (U+016F): L<<71.0,520.0>--<207.0,521.0>>                                                                                                             
                                                                                                                                                                       
          * utilde (U+0169): L<<314.0,154.0>--<315.0,362.0>>                                                                                                           
                                                                                                                                                                       
          * utilde (U+0169): L<<486.0,377.0>--<485.0,124.0>>                                                                                                           
                                                                                                                                                                       
          * utilde (U+0169): L<<71.0,520.0>--<207.0,521.0>>                                                                                                            
                                                                                                                                                                       
          * w (U+0077): L<<377.0,0.0>--<195.0,1.0>>                                                                                                                    
                                                                                                                                                                       
          * wacute (U+1E83): L<<377.0,0.0>--<195.0,1.0>>                                                                                                               
                                                                                                                                                                       
          * wcircumflex (U+0175): L<<377.0,0.0>--<195.0,1.0>>                                                                                                          
                                                                                                                                                                       
          * wdieresis (U+1E85): L<<377.0,0.0>--<195.0,1.0>>                                                                                                            
                                                                                                                                                                       
          * wgrave (U+1E81): L<<377.0,0.0>--<195.0,1.0>>                                                                                                               
                                                                                                                                                                       
          * z (U+007A): L<<115.0,520.0>--<456.0,519.0>>                                                                                                                
                                                                                                                                                                       
          * z (U+007A): L<<412.0,0.0>--<22.0,-1.0>>                                                                                                                    
                                                                                                                                                                       
          * zacute (U+017A): L<<115.0,520.0>--<456.0,519.0>>                                                                                                           
                                                                                                                                                                       
          * zacute (U+017A): L<<412.0,0.0>--<22.0,-1.0>>                                                                                                               
                                                                                                                                                                       
          * zcaron (U+017E): L<<115.0,520.0>--<456.0,519.0>>                                                                                                           
                                                                                                                                                                       
          * zcaron (U+017E): L<<412.0,0.0>--<22.0,-1.0>>                                                                                                               
                                                                                                                                                                       
          * zdotaccent (U+017C): L<<115.0,520.0>--<456.0,519.0>>                                                                                                       
                                                                                                                                                                       
          * zdotaccent (U+017C): L<<412.0,0.0>--<22.0,-1.0>> [code: found-semi-vertical]                                                                               
                                                                                                                                                                       

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
                                                                                                                                                                       
         Your font does not cover the following languages that require the soft-dotted feature: Nateni (Latn, 100,000 speakers), Ebira (Latn, 2,200,000 speakers),     
         Mundani (Latn, 34,000 speakers), Ukrainian (Cyrl, 29,273,587 speakers), Ejagham (Latn, 120,000 speakers), Mango (Latn, 77,000 speakers), Lugbara (Latn,       
         2,200,000 speakers), Belarusian (Cyrl, 10,064,517 speakers), Makaa (Latn, 221,000 speakers), Ma’di (Latn, 584,000 speakers), Sar (Latn, 500,000 speakers),    
         Yala (Latn, 200,000 speakers), Dan (Latn, 1,099,244 speakers), Southern Kisi (Latn, 360,000 speakers), Fur (Latn, 1,230,163 speakers), Koonzime (Latn,        
         40,000 speakers), Ekpeye (Latn, 226,000 speakers), Cicipu (Latn, 44,000 speakers), Dii (Latn, 71,000 speakers), Aghem (Latn, 38,843 speakers), Ijo,           
         Southeast (Latn, 2,471,000 speakers), Navajo (Latn, 166,319 speakers), Zapotec (Latn, 490,000 speakers), Bafut (Latn, 158,146 speakers), Basaa (Latn,         
         332,940 speakers), Kpelle, Guinea (Latn, 622,000 speakers), Vute (Latn, 21,000 speakers), Igbo (Latn, 27,823,640 speakers), South Central Banda (Latn,        
         244,000 speakers), Gulay (Latn, 250,478 speakers), Mfumte (Latn, 79,000 speakers), Nzakara (Latn, 50,000 speakers), Dutch (Latn, 31,709,104 speakers), Kom    
         (Latn, 360,685 speakers), Avokaya (Latn, 100,000 speakers), Ngbaka (Latn, 1,020,000 speakers), Bete-Bendi (Latn, 100,000 speakers). [code: soft-dotted]       

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
                                                                                                                                                                       
          • U+02C7 CARON: try adding one of: canadian-aboriginal, yi, tifinagh                                                                                         
          • U+02D8 BREVE: try adding one of: canadian-aboriginal, yi                                                                                                   
          • U+02D9 DOT ABOVE: try adding one of: canadian-aboriginal, yi                                                                                               
          • U+02DB OGONEK: try adding one of: canadian-aboriginal, yi                                                                                                  
          • U+02DD DOUBLE ACUTE ACCENT: not included in any glyphset definition                                                                                        
          • U+0302 COMBINING CIRCUMFLEX ACCENT: try adding one of: cherokee, math, tifinagh, coptic                                                                    
          • U+0306 COMBINING BREVE: try adding one of: old-permic, tifinagh                                                                                            
          • U+0307 COMBINING DOT ABOVE: try adding one of: coptic, canadian-aboriginal, tai-le, malayalam, syriac, math, old-permic, tifinagh                          
          • U+030A COMBINING RING ABOVE: try adding syriac                                                                                                             
          • U+030B COMBINING DOUBLE ACUTE ACCENT: try adding one of: osage, cherokee                                                                                   
          • U+030C COMBINING CARON: try adding one of: cherokee, tai-le                                                                                                
          • U+0326 COMBINING COMMA BELOW: not included in any glyphset definition                                                                                      
          • U+0327 COMBINING CEDILLA: not included in any glyphset definition                                                                                          
          • U+0328 COMBINING OGONEK: not included in any glyphset definition                                                                                           
          • U+1EBC LATIN CAPITAL LETTER E WITH TILDE: try adding vietnamese                                                                                            
          • U+1EBD LATIN SMALL LETTER E WITH TILDE: try adding vietnamese                                                                                              
          • U+2190 LEFTWARDS ARROW: try adding one of: symbols, math                                                                                                   
          • U+2192 RIGHTWARDS ARROW: try adding one of: symbols, math                                                                                                  
          • U+2194 LEFT RIGHT ARROW: try adding one of: symbols, math                                                                                                  
          • U+2195 UP DOWN ARROW: try adding one of: symbols, math                                                                                                     
          • U+2196 NORTH WEST ARROW: try adding one of: symbols, math                                                                                                  
          • U+2197 NORTH EAST ARROW: try adding one of: symbols, math                                                                                                  
          • U+2198 SOUTH EAST ARROW: try adding one of: symbols, math                                                                                                  
          • U+2199 SOUTH WEST ARROW: try adding one of: symbols, math                                                                                                  
                                                                                                                                                                       
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

    Result: FAIL

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
                                                                                                                                                                       
    FAIL License file OFL.txt exists but NameID 13 (LICENSE DESCRIPTION) value on platform 3 (WINDOWS) is not specified for that. Value was: "This Font Software is    
         licensed under the SIL Open Font License, Version 1.1. This license is available with a FAQ at:                                                               
         https://openfontlicense.org" Must be changed to "This Font Software is licensed under the SIL Open Font License, Version 1.1. This license is available with  
         a FAQ at: https://openfontlicense.org" [code: wrong]                                                                                                          

    Result: FAIL

 >> com.google.fonts/check/name/line_breaks
    Name table entries should not contain line-breaks.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    There are some entries on the name table that may include more than one line of text. The Google Fonts team, though, prefers to keep the name table entries short  
    and simple without line breaks.                                                                                                                                    
                                                                                                                                                                       
    For instance, some designers like to include the full text of a font license in the "copyright notice" entry, but for the GFonts collection this entry should      
    only mention year, author and other basic info in a manner enforced by com.google.fonts/check/font_copyright                                                       
                                                                                                                                                                       
    FAIL Name entry LICENSE_DESCRIPTION on platform WINDOWS contains a line-break. [code: line-break]                                                                  

    Result: FAIL

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

    Result: FAIL

 >> com.google.fonts/check/glyph_coverage
    Check Google Fonts glyph coverage.
    with Brokken-Bold.ttf

    Rationale:                                                                
                                                                                                                                                                       
    Google Fonts expects that fonts in its collection support at least the minimal set of characters defined in the `GF-latin-core` glyph-set.                         
                                                                                                                                                                       
    More info: https://github.com/fonttools/fontbakery/pull/2488

    FAIL Missing required codepoints:                                                                                                                                  
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x005E (CIRCUMFLEX ACCENT)                                                                                                                                 
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00A2 (CENT SIGN)                                                                                                                                         
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00A3 (POUND SIGN)                                                                                                                                        
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00A5 (YEN SIGN)                                                                                                                                          
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00A9 (COPYRIGHT SIGN)                                                                                                                                    
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00AA (FEMININE ORDINAL INDICATOR)                                                                                                                        
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00AE (REGISTERED SIGN)                                                                                                                                   
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00B6 (PILCROW SIGN)                                                                                                                                      
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00B7 (MIDDLE DOT)                                                                                                                                        
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00BA (MASCULINE ORDINAL INDICATOR)                                                                                                                       
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00D7 (MULTIPLICATION SIGN)                                                                                                                               
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x00F7 (DIVISION SIGN)                                                                                                                                     
                                                                                                                                                                       
                                                                                                                                                                       
          - 0x2122 (TRADE MARK SIGN)                                                                                                                                   
                                                                                                                                                                       
                                                                                                                                                                       
         [code: missing-codepoints]                                                                                                                                    

    Result: FAIL

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

    Result: FAIL

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

Total:
    ERROR: 0
    FATAL: 0
    FAIL: 6
    WARN: 11
    INFO: 8
    SKIP: 118
    PASS: 105
