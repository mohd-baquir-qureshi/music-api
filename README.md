
# Music API (Free Search & Stream)

## Deprecation Notice
---
###### **NOTE:** We regret to inform you that the current version of Music API will be deprecated as of 13th May 2024.
 ---

This is a free unofficial API to Search and Stream High Quality (320kbps) music from popular music streaming engines without any restrictions.

---
###### **NOTE:** Most of the time you will get 320 Kbps High Quality Audio only, but if it is not available then it will fetch the medium quality audio.
 ---
## API Reference

#### Search Song

```
  GET https://musicapi.x007.workers.dev/search
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `q` | `string` | **Required**. Song Name |
| `searchEngine` | `string` | **Required**. Music Search Engine Name (Available Search Engine Names - gaama,seevn,hunjama,mtmusic,wunk) |

#### Search Song Example

```
  GET https://musicapi.x007.workers.dev/search?q=Pathaan&searchEngine=gaama
```

```json
{
    "status": 200,
    "response": [
        {
            "id": "e9b525b48070ce18657a03a7be249d0c96b18bf012ba2ce87f33097dd45b8a4047f5b7c16dd94923040fbb5b4d83ee46",
            "title": "Jhoome Jo Pathaan",
            "img": "https://hls-server.vercel.app/img/fd05eacd27592b53153fc715257ddf3fe71a60eb063e4975190df148dafd38e0c5b1d1fc5e9e1a8d78a0e601e775b2780e561e59a61f94b20e0ef4e599f7da999c57233ac8921a96cba8b23d52be0344"
        },
        {
            "id": "aeed2c96e7313c3a10c3ef220b768d11d90bd7e6f2c542d651c07d2ac205e08634290fd2c4b90bc221775bed81b9f037",
            "title": "Pathaan’s Theme",
            "img": "https://hls-server.vercel.app/img/fd05eacd27592b53153fc715257ddf3fe71a60eb063e4975190df148dafd38e0c5b1d1fc5e9e1a8d78a0e601e775b2780e561e59a61f94b20e0ef4e599f7da999c57233ac8921a96cba8b23d52be0344"
        },
        {
            "id": "3be37852a755fe94e41199e1e715a84c639dc9af30f9d992645418cd00d746061493acc356e1b8ac2d28fee430844602",
            "title": "Besharam Rang (From \"Pathaan\")",
            "img": "https://hls-server.vercel.app/img/fd05eacd27592b53153fc715257ddf3fe71a60eb063e4975190df148dafd38e0667da290b1493560f4e7a5233872210b4a53693dc9102a43df4e5cfdc7112d85cc34ebac5af4de99d58c36fcad6618fb"
        }
    ],
    "message": "success"
}
```

#### Get Song Lyrics

```
  GET https://musicapi.x007.workers.dev/lyrics
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Song ID Fetched from Search Response |

---
###### **NOTE:** It is Only for Gaama search engine, and it is in Beta Mode, so it might not work for some songs.
 ---

#### Get Song Lyrics Example

```
  GET https://musicapi.x007.workers.dev/lyrics?id=e9b525b48070ce18657a03a7be249d0c96b18bf012ba2ce87f33097dd45b8a4047f5b7c16dd94923040fbb5b4d83ee46
```

```json
{
    "status": 200,
    "response": "<p><p>Tumne Mohabbat Karni Hai</p></p><p><p>Humne Mohabbat Ki Hai</p></p><p>......",
    "message": "success"
}
```

#### Fetch Song

```
  GET https://musicapi.x007.workers.dev/fetch
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Song ID Fetched from Search Response |


#### Fetch Song Example (Gaama) HLS Stream Link

```
  GET https://musicapi.x007.workers.dev/fetch?id=e9b525b48070ce18657a03a7be249d0c96b18bf012ba2ce87f33097dd45b8a4047f5b7c16dd94923040fbb5b4d83ee46
```

```json
{
	"status": 200,
	"response": "https://hls-server.vercel.app/m3u8/b69f162ec82bb5aa0af24fdbf77f852c646e2449cc5ef9554bf8eae5fdadf1d2a4ea93fa79729f371497772084cd5e9709affc42e1aeecc20d5ad222aa959e2ffa1398416ca6e3a6759275db98b69daddb552107c43d67f8534aef763ce0624a8f42f6963263dc4f76d1497b24af27d507d659a636f96f97f735f1f0f7c78f86c38f419136f0c60ec738490aa0bc5d41b1fed91856472b4834f894d7b6f0d41cf68eb09f0178d1ffe78ebfd9fa21d04a0ea75a269798fa747f55699f7b881059.m3u8",
	"message": "success"
}
```

---
###### **NOTE:** The above fetch song response is only for "gaama" search engine, for rest of the search engines you will get direct mp3 or mp4 file, see the example below.
 ---

#### Fetch Song Example (Other Search Engines) Direct Mp3 File

```
  GET https://musicapi.x007.workers.dev/fetch?id=205659dc7589f400defc73f6918b369759cd3b88cfaef01c5af3c98af7e10d683d55756d7191f1217deea14ee68a618ca8aba082073c68e1b8bef0b3aa416375
```

Made with ❤️ in India.
