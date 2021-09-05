# Mersenne Primes

[Prime numbers](https://en.wikipedia.org/wiki/Prime_number) are awesome!  If you are not intrigued by prime numbers and how important they are in all of mathematics, you are missing out.  At least to my mind.  However, this post is about a specific _type_ of prime number, [Mersenne primes](https://en.wikipedia.org/wiki/Mersenne_prime).  Mersenne primes are the type of prime numbers that you search for when you are trying to find a new world record for the largest known prime number.  The reason we search for Mersenne primes and not other types of prime numbers is because there are faster algorithms for finding Mersenne primes compared to algorithms for general prime numbers.  The [Lucas-Lehmer test](https://en.wikipedia.org/wiki/Lucas%E2%80%93Lehmer_primality_test) is the most popular algorithm used for searching for large Mersenne prime numbers.

So why am I searching for the next new world record for the largest known prime number?  Two reasons:

1. Math and being part history by finding the new world record largest prime number
2. Prizes. See [Electronic Frontier Foundation](https://www.eff.org/awards/coop) for more details

The odds of finding a new world record largest prime number are low but there is a collaborated search for them on the internet known as [GIMPS](https://www.mersenne.org/), which stands for the Great Internet Mersenne Prime Search.

To give you an idea of how large the prime numbers we are searching for are, we will compare the size of these primes numbers to the approximate number of atoms in the Universe.  The [number of atoms in the observable Universe](https://en.wikipedia.org/wiki/Observable_universe#Matter_content%E2%80%94number_of_atoms) has been stated to be approximately 10<sup>80</sup> atoms.  If we were to write this down on paper, that would be the number 1 followed by 80 zeros.  Obviously all the atoms in the observable Universe is a big number but the primes that will win you the prize in the above contest is a prime number with 100 million decimal digits.  If you were to write down this number on paper starting with a 1, like before, we would then need to follow it with 100 million other numbers, not just 80 zeros.  The difference is enormous.  This comparision give us an idea of just how large these prime numbers are that we are searching for.  They are much larger than the approximated number of atoms in the observable Universe!

In order to search for these large primes, obviously you need to be running algorithms that search for them such as the Lucas-Lehmer test mentioned above.  On top of that, these types of algorithms are much faster on GPUs than your standard CPU.  Below is a parts list of the hardware for the computer I built to search for Mersenne primes.  

## Hardware Parts List
```
* HyperX Fury 16GB 2666MHz DDR4 CL 16 DIMM Black XMP Desktop Memory Single Stick HX426C16FB3/16
* ROSEWILL Gaming 80 Plus Gold 1600W Power Supply/PSU: HERCULES-1600S
* Intel Core i5-9400F Desktop Processor 6 Cores 4.1 GHz Turbo Without Graphics
* Plugable USB 2.0 Wireless N 802.11n 150 Mbps Nano WiFi Network Adapter (Realtek RTL8188EUS Chipset)
* Kingston 120GB A400 SATA 3 2.5" Internal SSD SA400S37/120G
* MSI Pro Series Intel Coffee Lake H310 LGA 1151 BTC ETH LTC Crypto Mining ATX Motherboard (H310-F PRO)
* Four - XFX AMD Radeon VII 16GB HBM2, 1750 MHz Boost, 1801 MHz Peak, 3xDP 1xHDMI Pci-E 3.0
* Ubit 6 Pack Latest PCI-E Riser Express Cable 16X to 1X (6pin / MOLEX/SATA) with Led Graphics Extension Ethereum ETH Mining Powered Riser Adapter Card+60cm USB 3.0 Cable
```

## Software
```
* Ubuntu 20.04.1 LTS Server
* [gpuowl](https://github.com/preda/gpuowl)
```

![Imgur](https://i.imgur.com/CSP1MMW.jpg)

![Imgur](https://i.imgur.com/d3Rlf2o.jpg)

![Imgur](https://i.imgur.com/0VrSVqm.jpg)

![Imgur](https://i.imgur.com/7ymw7Dc.jpg)
