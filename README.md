# KBBI SQL Database
KBBI SQL Database, total data ```115.978``` kata.
Tersedia untuk ```MySQL```, ```SQLite``` dan ```PostgreSQL```.

## Buat Tabel Baru
Sebelum mengimpor data kata, buatlah tabelnya terlebih dahulu.

### SQLite
| Nama Field | Tipe Data | Nullable | Keterangan                  |
|------------|-----------|----------|-----------------------------|
| _id        | INTEGER   | NO       | Primary Key, Auto Increment |
| word       | TEXT      | NO       | Kata                        |
| arti       | TEXT      | NO       | Arti atau penjelasan        |
| type       | INTEGER   | NO       | Tipe atau kategori          |

```sql
CREATE TABLE "dictionary" (
  _id INTEGER PRIMARY KEY AUTOINCREMENT,
  word TEXT NOT NULL,
  arti TEXT NOT NULL,
  type INTEGER NOT NULL
);
```

### PostgrSQL
| Nama Field | Tipe Data | Nullable | Keterangan                  |
|------------|-----------|----------|-----------------------------|
| _id        | serial4   | NO       | Primary Key, Auto Increment |
| word       | text      | NO       | Kata                        |
| arti       | text      | NO       | Arti atau penjelasan        |
| type       | int4      | NO       | Tipe atau kategori          |

```sql
CREATE TABLE public."dictionary" (
	"_id" serial4 NOT NULL,
	word text NOT NULL,
	arti text NOT NULL,
	"type" int4 NOT NULL,
	CONSTRAINT dictionary_pkey PRIMARY KEY (_id)
);
```

### MySQL
| Nama Field | Tipe Data | Nullable | Keterangan                  |
|------------|-----------|----------|-----------------------------|
| _id        | INT(11)   | NO       | Primary Key, Auto Increment |
| word       | TEXT      | NO       | Kata                        |
| arti       | TEXT      | NO       | Arti atau penjelasan        |
| type       | INT(11)   | NO       | Tipe atau kategori          |

```sql
CREATE TABLE `dictionary` (
  `_id` int(11) NOT NULL AUTO_INCREMENT,
  `word` text NOT NULL,
  `arti` text NOT NULL,
  `type` int(11) NOT NULL,
  PRIMARY KEY (`_id`)
) ENGINE=InnoDB AUTO_INCREMENT=115989 DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;
```

## API KBBI
Jika data pada database kurang lengkap, Anda dapat mengkombinasikannya dengan [API KBBI](https://github.com/dyazincahya/API-KBBI-PHP-Codeigniter-4) yang sumber datanya langsung berasal dari [KBBI Daring Kemdikbud](https://kbbi.kemdikbud.go.id/)
