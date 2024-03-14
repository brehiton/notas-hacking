## Objetivo
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.
## Pistas
Try fixing the file header
## Solucion
```
──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ ls
mystery
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ file mystery 
mystery: data
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ xxd mystery | head
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*"3o.[U.==. ..
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ hexeditor mystery      
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ xxd mystery | head
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4322 4452  .PNG........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*"3o.[U.==. ..
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ hexeditor mystery
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ ls
mystery
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ file mystery
mystery: data
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ hexeditor mystery
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ file mystery
mystery: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ open mystery                     
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ sudo apt install pngcheck  
[sudo] password for hectorr: 
Sorry, try again.
[sudo] password for hectorr: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  cython3 debtags kali-debtags libboost-dev libboost1.83-dev
  libhiredis0.14 libjavascriptcoregtk-4.0-18 libopenblas-dev
  libopenblas-pthread-dev libopenblas0 libperl5.36 libpython3-all-dev
  libpython3.12 libpython3.12-dev libqt5multimedia5
  libqt5multimedia5-plugins libqt5multimediagsttools5
  libqt5multimediawidgets5 librtlsdr0 libucl1 libwebkit2gtk-4.0-37
  libxsimd-dev libzxing2 perl-modules-5.36 python3-all-dev
  python3-backcall python3-beniget python3-debian python3-future
  python3-gast python3-pickleshare python3-pythran
  python3-requests-toolbelt python3-rfc3986 python3-unicodecsv
  python3.12-dev xtl-dev
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
  pngcheck
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 68.6 kB of archives.
After this operation, 208 kB of additional disk space will be used.
Get:1 http://kali.download/kali kali-rolling/main amd64 pngcheck amd64 3.0.3-3 [68.6 kB]
Fetched 68.6 kB in 1s (84.8 kB/s)   
Selecting previously unselected package pngcheck.
(Reading database ... 423877 files and directories currently installed.)
Preparing to unpack .../pngcheck_3.0.3-3_amd64.deb ...
Unpacking pngcheck (3.0.3-3) ...
Setting up pngcheck (3.0.3-3) ...
Processing triggers for man-db (2.12.0-3) ...
Processing triggers for kali-menu (2023.4.7) ...
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ pngcheck -v mystery    
zlib warning:  different version (expected 1.2.13, using 1.3)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in mystery
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ hexeditor mystery
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in mystery
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ hexeditor mystery  
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in mystery
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ hexeditor mystery
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
  chunk IDAT at offset 0x10008, length 65524
  chunk IDAT at offset 0x20008, length 65524
  chunk IDAT at offset 0x30008, length 6304
  chunk IEND at offset 0x318b4, length 0
No errors detected in mystery (9 chunks, 96.3% compression).
                                                                            
┌──(hectorr㉿kali2024)-[~/picoCTF/Forensic/c0rrupt]
└─$ open mystery

picoCTF{c0rrupt10n_1847995}
```

## Notas adicionales 
hicimos el uso de diferentes herraminetas como hexeditor para cambiarle y quitarle lo corrupto tambien para comprobar si esta bien la imagen con la aplicacion **pngcheck -v** que te dice como esta la imagen ademas de la pagina que nos ayudo como debe de ir una imagen
## Referencias 
https://en.wikipedia.org/wiki/List_of_file_signatures