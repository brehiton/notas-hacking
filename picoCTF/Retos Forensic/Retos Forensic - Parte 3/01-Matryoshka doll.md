
## Objetivo
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/f6cc2560a70b1ea811c151accba5390f/dolls.jpg)
## Pistas
Wait, you can hide files inside files? But how do you find them?

Make sure to submit the flag as picoCTF{XXXXX}
## Solucion
```
──(hectorr㉿kali2024)-[~/picoCTF/Forensic/Matryoshka doll]
└─$ binwalk -e dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378955, uncompressed size: 383936, name: base_images/2_c.jpg
651613        0x9F15D         End of Zip archive, footer length: 22

                                                                                 
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/Matryoshka doll]
└─$ ls
_dolls.jpg.extracted  dolls.jpg
                                                                                 
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/Matryoshka doll]
└─$ cd _dolls.jpg.extracted 
                                                                                 
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/Matryoshka doll/_dolls.jpg.extracted]
└─$ ls
4286C.zip  base_images
                                                                                 
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/Matryoshka doll/_dolls.jpg.extracted]
└─$ cd base_images         
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/Forensic/Matryoshka doll/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/Forensic/Matryoshka doll/_dolls.jpg.extracted/base_images]
└─$ open 2_c.jpg 
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/Forensic/Matryoshka doll/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/Forensic/Matryoshka doll/_dolls.jpg.extracted/base_images]
└─$ binwalk -e 2_c.jpg  

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196041, uncompressed size: 201443, name: base_images/3_c.jpg
383803        0x5DB3B         End of Zip archive, footer length: 22
383914        0x5DBAA         End of Zip archive, footer length: 22

                                                                                 
┌──(hectorr㉿kali2024)-[~/…/Forensic/Matryoshka doll/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg  _2_c.jpg.extracted
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/Forensic/Matryoshka doll/_dolls.jpg.extracted/base_images]
└─$ cd _2                  
cd: no such file or directory: _2
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/Forensic/Matryoshka doll/_dolls.jpg.extracted/base_images]
└─$ cd _2_c.jpg.extracted 
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/Matryoshka doll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ ls
2DD3B.zip  base_images
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/Matryoshka doll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ cd base_images       
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk -e 3_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77649, uncompressed size: 79806, name: base_images/4_c.jpg
201421        0x312CD         End of Zip archive, footer length: 22

                                                                                 
┌──(hectorr㉿kali2024)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg  _3_c.jpg.extracted
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ cd _3_c.jpg.extracted 
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ ls
1E2D6.zip  base_images
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ cd base_images       
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk -e 4_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 62, uncompressed size: 81, name: flag.txt
79784         0x137A8         End of Zip archive, footer length: 22

                                                                                 
┌──(hectorr㉿kali2024)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg  _4_c.jpg.extracted
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4                
cd: no such file or directory: _4
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted 
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                                 
┌──(hectorr㉿kali2024)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt         


picoCTF{ac0072c423ee13bfc0b166af72e25b61}
```
## Notas adicionales 
hicimos el uso de **binwalk -e** para que nos subtraiga lo que tenga dentro la imgaen en este caso tenia varias imagenes en ella 
## Referencias 