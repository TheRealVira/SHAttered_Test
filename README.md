# SHAttered_Test
Testing out if the SHA-1 could really break in practice.

(Source: http://shattered.io/)

## Description

> We have broken SHA-1 in practice.

> This industry cryptographic hash function standard is used for digital signatures and file integrity verification, and protects a wide spectrum of digital assets, including credit card transactions, electronic documents, open-source software repositories and software updates.

> It is now practically possible to craft two colliding PDF files and obtain a SHA-1 digital signature on the first PDF file which can also be abused as a valid signature on the second PDF file.

> For example, by crafting the two colliding PDF files as two rental agreements with different rent, it is possible to trick someone to create a valid signature for a high-rent contract by having him or her sign a low-rent contract.

## Testing

For testing purpose I am using my default operating system ([Elementary OS](https://elementary.io/)). I have already downlaoded the files, which are supposed to have equal Sha-1 hahses! (Speaking of "`shattered-1.pdf`" and "`shattered-2.pdf`")

When calculating the Sha-1 hashes the results are stunning:

shattered-1.pdf:  `38762cf7f55934b34d179ae6a4c80cadccbb7f0a`<br /> 
shattered-2.pdf:  `38762cf7f55934b34d179ae6a4c80cadccbb7f0a`

For those how do not see it by now - those two strings/hashes are **equal**, which is like really really bad!

## Results copied from the terminal
```
vira@DerLaptop:~/Documents/Shattered/SHAttered_Test$ ls
LICENSE  README.md  shattered-1.pdf  shattered-2.pdf
vira@DerLaptop:~/Documents/Shattered/SHAttered_Test$ sha1sum shattered-1.pdf 
38762cf7f55934b34d179ae6a4c80cadccbb7f0a  shattered-1.pdf
vira@DerLaptop:~/Documents/Shattered/SHAttered_Test$ sha1sum shattered-2.pdf 
38762cf7f55934b34d179ae6a4c80cadccbb7f0a  shattered-2.pdf
vira@DerLaptop:~/Documents/Shattered/SHAttered_Test$ diff  <(echo "38762cf7f55934b34d179ae6a4c80cadccbb7f0a" ) <(echo "38762cf7f55934b34d179ae6a4c80cadccbb7f0a")
vira@DerLaptop:~/Documents/Shattered/SHAttered_Test$ 
```
