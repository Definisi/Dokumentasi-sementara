### Algoritma MQ135, Arduino ESP8266 dan Relay
**Hasil dari pengecekan yang di lakukan, hasilnya seperti berikut.**

| Nomor | CO2      | Kondisi Relay                                                |
| ----- | -------- | ------------------------------------------------------------ |
| 1     | 400>     | Semua relay tidak aktif                                      |
| 2     | 500-700  | Relay 1 ( Kabel Hijau ) Aktif, Sisanya tidak aktif           |
| 3     | 700-1000 | Relay 2 ( Kabel Biru ) Aktif, Sisanya tidak aktif            |
| 4     | 1000<    | Relay 3 ( Kabel Putih dan Kipas ) Aktif, Sisanya tidak aktif |

Dari hasil pengujian terdapat relay yang aktif di tandai dengan matinya lampu relay yang berwarna merah, untuk relay yang tidak aktif di tandai dengan nyalanya lampu di relay.