# Verifisering av krypterte data

Problemet er at vi bruker [NaCl
Secretbox](https://en.wikipedia.org/wiki/NaCl_(software)) "based on
XSalsa20 cipher and Poly1305 for integrity", pakket inn i et
komersielt produkt.  

Som en del av "disaster recovery" ønsker vi å verifisere at vi kan
dekryptere det programvaren lager.


## Hva er XSalsa20

>In 2008, Bernstein proposed a variant of Salsa20 with 192-bit nonces
>called XSalsa20.[7][8][9] XSalsa20 is provably secure if Salsa20 is
>secure, but is more suitable for applications where longer nonces are
>desired. XSalsa20 feeds the key and the first 128 bits of the nonce
>into one block of Salsa20 (without the final addition, which may
>either be omitted, or subtracted after a standard Salsa20 block), and
>uses 256 bits of the output as the key for standard Salsa20 using the
>last 64 bits of the nonce and the stream position. Specifically, the
>256 bits of output used are those corresponding to the non-secret
>portions of the input: indexes 0, 5, 10, 15, 6, 7, 8 and 9. 

Detaljer i `xsalsa-20110204.pdf` lokalt her.

## Hva er Poly1305

Poly1305  tar en 16-byte hemmelighet r og en melding av lengde L
(bytes) og genererer et 16-bytes fingeravtrykk.

Detaljer i `poly1305-20050329.pdf` lokalt her.


## Filen "rclone.config"
Dette er konfigurasjonsfilen som benyttes for å synkronisere filer fra
en source til en destination. Denne filen inneholder da faktisk
password og password2 over. Her tror jeg kanskje at krypteringen er av
en annen type, men ikke sikker. Dokumentasjonen til Rclone sier
følgende: "The obscured password is created using AES-CTR with a
static key."

AES-CTR betyr klassisk [counter
mode](https://en.wikipedia.org/wiki/Block_cipher_mode_of_operation#Counter_(CTR)).

For filen "rclone.conf" (tilgjengelig lokalt) så er password: DY7DXQ341WH1AIZINM2U


Password: iWI7jRkNI4UuYTdIymZ2bh8c9lZ-Np9EmJ-djdShwTaJM7ofhe0rxBdiUO8VvZA11wg8SIhSGba6cwVQtOGE3oi9GgWTFDAcptXJkJQW3VobdKR_nnU44jZN2Ib7D5fvThzuyP-gWMP2vd-ri53qDPVXURUKJsZZqrxypqlxKss

Password2: zCAU4y4a6jNBPxb0si35imy6JTPw2QRlh8JYjAGINg0EUJ-QDl0eAKGz5G9HpwKH8HMSfskAOqGDKqLce74_8mbmHutM3Q3Kj9kdq9nMFqvmDkLRjQtScpMvKL4dxZCHp2wh3Wo5F7vP5goOYsDPCik_rC95lh1gaOGZYD1JEEs

