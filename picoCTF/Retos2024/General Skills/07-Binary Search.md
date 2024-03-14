## Objetivo
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/17/challenge.zip)

Additional details will be available after launching your challenge instance.
## Pistas
Have you ever played hot or cold? Binary search is a bit like that.

You have a very limited number of guesses. Try larger jumps between numbers!

The program will randomly choose a new number each time you connect. You can always try again, but you should start your binary search over from the beginning - try around 500. Can you think of why?
## Solucion
```
─(hectorr㉿kali2024)-[~/picoCTF/Retos2024/General Skills]
└─$ ssh -p 62899 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:62899 ([18.217.83.136]:62899)' can't be established.
ED25519 key fingerprint is SHA256:M8hXanE8l/Yzfs8iuxNsuFL4vCzCKEIlM/3hpO13tfQ.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:62899' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 250
Higher! Try again.
Enter your guess: 375
Higher! Try again.
Enter your guess: 437
Higher! Try again.
Enter your guess: 467
Higher! Try again.
Enter your guess: 483
Higher! Try again.
Enter your guess: 492
Lower! Try again.
Enter your guess: 488
Lower! Try again.
Enter your guess: 486
Higher! Try again.
Enter your guess: 487
Congratulations! You guessed the correct number: 487
Here's your flag: picoCTF{g00d_gu355_6dcfb67c}
Connection to atlas.picoctf.net closed.
```
## Notas adicionales 
estuvimos utilizando la logica de mitad y mitad para poder encontrar mas rapido la bandera un ejemplo era 1000 y de esos la mitad fue de 500 y luego de 250
## Referencias 