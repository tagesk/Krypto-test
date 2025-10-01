# Krypto-test

Her er problemet:

Vi benytter [NaCl Secretbox](https://en.wikipedia.org/wiki/NaCl_(software)) "based on
XSalsa20 cipher and Poly1305 for integrity.

## Hva er XSalsa20
XSalsa20 with 192-bit nonceIn 2008, Bernstein proposed a variant of
Salsa20 with 192-bit nonces called XSalsa20 (PDF i
katalogen). XSalsa20 is provably secure if Salsa20 is secure, but is
more suitable for 
applications where longer nonces are desired. XSalsa20 feeds the key
and the first 128 bits of the nonce into one block of Salsa20 (without
the final addition, which may either be omitted, or subtracted after a
standard Salsa20 block), and uses 256 bits of the output as the key
for standard Salsa20 using the last 64 bits of the nonce and the
stream position. Specifically, the 256 bits of output used are those
corresponding to the non-secret portions of the input: indexes 0, 5,
10, 15, 6, 7, 8 and 9.

## Filen "rclone.config"
Dette er konfigurasjonsfilen som benyttes for å synkronisere filer fra
en source til en destination. Denne filen inneholder da faktisk
password og password2 over. Her tror jeg kanskje at krypteringen er av
en annen type, men ikke sikker. Dokumentasjonen til Rclone sier
følgende: "The obscured password is created using AES-CTR with a
static key."

AES-CTR betyr klassisk [counter
mode](https://en.wikipedia.org/wiki/Block_cipher_mode_of_operation#Counter_(CTR)).

For filen "rclone.conf" så er password: DY7DXQ341WH1AIZINM2U

rclone.conf
# Encrypted rclone configuration File

RCLONE_ENCRYPT_V0:
1HXr6heXEgsGECAa+tLUqTyf8sk4T1oJXQaiX3EDImHeLmay4fE6kB0u9SPijDvtIoOQb/14Hdjbjz9FCDnvGGR1ao+431saP1aTtxMLNe8R8uAHwJUPuMIvjGE3XSlFlUzgN+WLbA+J8mPV0x6nxjPw0dmmFnugiCL/5edjWha6rawS2cw9E/lqloZdgRvQoIf/KUaM5dLTaOl9V+rynanfG+3txy3vBFu4bypdK5uUABq7LLwCgE5q61S7LbsAUchzUwtdXYUcZy8itle/oI2QPIE0kIMG7qgJMYYbUudDWZfGQ6GIOD69eaTrKLrADfJTwoh958THlQo6Z7I9wHPtSEClcpdGnYb1v7fVFlMAhEemZwzR8noB6tImDUdnDCBh/lRdV664dftJLFjTM5AF1y7/3CbnFHEtHqqGbbUzQ6FVpGANAScS2k1kBDDDZvudwYtCtVzYsT4uNPY5Wyl9PrNr/QzRXCi6bYHaCcrAQyMxBPkVmbuRrPbGfAb5fAbR59BQHsfnGc+otMLcvomMQ0/VXwOyOXhWiu0WOY98kkzcppFU3HYYmKdURsvZIZhv8IB7rLiG2mI2gLs35Y57GtiiQ13UK16cZG6UKs4e71sA5pE3t5WTOz0zs+Xegve2GvgbYYqoJFweBFWnpZl4sz9lIhQFsCe8bH9qJDxl7ZZy3I4BCJGMFMnCHCWJafuYtNYF5Qyi7/m218AWu8LDCIrdJx4sbNnhmcF4Nco0uY97NDD++67OR9OP/Rf3B/HqqbN+weSFl/XMravR6ej5IacJIrm0EOrT8bMt+Hf5/PMYNf5O+6xzMvvSRxxmnI3TWK2wsZADeTWwzOWtR/MLRTs/DxwsW+yxA8fcqSRSdyFcor0LDUM9uzA/av9kwq9eGEV7bIZ/uaIMx1bbVY2W+BQyrsuMmrTSrBQUYbaNpIVd4lIiQt3dqxbkTfdtd3M33jsiTpVIwwMwEeoBW2XS914S1DXCK75TUT6PpeyTnmqTRYu0bSNFFBmRh8RqILpmbRzhpQU= 


Password: iWI7jRkNI4UuYTdIymZ2bh8c9lZ-Np9EmJ-djdShwTaJM7ofhe0rxBdiUO8VvZA11wg8SIhSGba6cwVQtOGE3oi9GgWTFDAcptXJkJQW3VobdKR_nnU44jZN2Ib7D5fvThzuyP-gWMP2vd-ri53qDPVXURUKJsZZqrxypqlxKss

Password2: zCAU4y4a6jNBPxb0si35imy6JTPw2QRlh8JYjAGINg0EUJ-QDl0eAKGz5G9HpwKH8HMSfskAOqGDKqLce74_8mbmHutM3Q3Kj9kdq9nMFqvmDkLRjQtScpMvKL4dxZCHp2wh3Wo5F7vP5goOYsDPCik_rC95lh1gaOGZYD1JEEs

