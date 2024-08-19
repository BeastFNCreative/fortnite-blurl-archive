# Tutorial

1. GET Request to [CMS - spark-tracks](https://fortnitecontent-website-prod07.ol.epicgames.com/content/api/pages/fortnite-game/spark-tracks)
2. Go into any songs JSON Data and look for `qi` (Depending on if used in code, you might have to unpack the JSON Data)
3. Inside the `qi` tag, you have to look for the sub tags: `sid` (songId), `pid` (previewId), `stereoId` (stereoSongId)
4. You're gonna use the UUID there to GET Request to [cdn.qstv.on.epicgames.com/UUID](https://cdn.qstv.on.epicgames.com/817406b8-7dc6-4122-92e6-65bc307f78cb) (replace UUID with your UUID)
5. Inside the response will be a `metadata` tag, go into that and then go into the `baseUrls` key
6. You will be provided with links to the asset on the streaming service, if you just want the VUID, you have to isolate it


# Examples

- `qi`

```json
{
  "sid": "9ca29287-60aa-4550-9d2d-278b6ef8c19d",
  "pid": "817406b8-7dc6-4122-92e6-65bc307f78cb",
  "title": "timeless",
  "tracks": [
    {
      "part": "ds",
      "channels": [
        "FL",
        "FR"
      ],
      "vols": [
        4,
        4
      ]
    },
    {
      "part": "bs",
      "channels": [
        "FL",
        "FR"
      ],
      "vols": [
        4,
        4
      ]
    },
    {
      "part": "gs",
      "channels": [
        "FL",
        "FR"
      ],
      "vols": [
        4,
        4
      ]
    },
    {
      "part": "vs",
      "channels": [
        "FL",
        "FR"
      ],
      "vols": [
        4,
        4
      ]
    },
    {
      "part": "fs",
      "channels": [
        "FL",
        "FR"
      ],
      "vols": [
        4,
        4
      ]
    }
  ],
  "preview": {
    "starttime": 100.851
  }
}
```

- cdn-qstv Response Example

```json
{
  "playlist": "PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4KPE1QRCB4bWxucz0idXJuOm1wZWc6ZGFzaDpzY2hlbWE6bXBkOjIwMTEiIHhtbG5zOnhzaT0iaHR0cDovL3d3dy53My5vcmcvMjAwMS9YTUxTY2hlbWEtaW5zdGFuY2UiIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB4c2k6c2NoZW1hTG9jYXRpb249InVybjptcGVnOkRBU0g6c2NoZW1hOk1QRDoyMDExIGh0dHA6Ly9zdGFuZGFyZHMuaXNvLm9yZy9pdHRmL1B1YmxpY2x5QXZhaWxhYmxlU3RhbmRhcmRzL01QRUctREFTSF9zY2hlbWFfZmlsZXMvREFTSC1NUEQueHNkIiBwcm9maWxlcz0idXJuOm1wZWc6ZGFzaDpwcm9maWxlOmlzb2ZmLWxpdmU6MjAxMSIgdHlwZT0ic3RhdGljIiBtZWRpYVByZXNlbnRhdGlvbkR1cmF0aW9uPSJQVDMwLjIxM1MiIG1heFNlZ21lbnREdXJhdGlvbj0iUFQyLjAwMFMiIG1pbkJ1ZmZlclRpbWU9IlBUNC4xMDZTIj4KICA8QmFzZVVSTD5odHRwczovL2ZvcnRuaXRlLXZvZC5ha2FtYWl6ZWQubmV0L2ZWQUxMWEJkQXV4VVZVbm5Rai83NWYwZGFhYi1jOGE1LTRjODMtOWVhOC02YjYwNGIwOWQ0MTcvPC9CYXNlVVJMPgogIDxQcm9ncmFtSW5mb3JtYXRpb24+PC9Qcm9ncmFtSW5mb3JtYXRpb24+CiAgPFBlcmlvZCBpZD0iMCIgc3RhcnQ9IlBUMFMiPgogICAgPEFkYXB0YXRpb25TZXQgaWQ9IjAiIGNvbnRlbnRUeXBlPSJhdWRpbyIgc3RhcnRXaXRoU0FQPSIxIiBzZWdtZW50QWxpZ25tZW50PSJ0cnVlIiBiaXRzdHJlYW1Td2l0Y2hpbmc9InRydWUiPgogICAgICA8UmVwcmVzZW50YXRpb24gaWQ9IjAiIGF1ZGlvU2FtcGxpbmdSYXRlPSI0ODAwMCIgYmFuZHdpZHRoPSIxMjgwMDAiIG1pbWVUeXBlPSJhdWRpby9tcDQiIGNvZGVjcz0ibXA0YS40MC4yIj4KICAgICAgICA8U2VnbWVudFRlbXBsYXRlIGR1cmF0aW9uPSIyMDAwMDAwIiB0aW1lc2NhbGU9IjEwMDAwMDAiIGluaXRpYWxpemF0aW9uPSJpbml0XyRSZXByZXNlbnRhdGlvbklEJC5tcDQiIG1lZGlhPSJzZWdtZW50XyRSZXByZXNlbnRhdGlvbklEJF8kTnVtYmVyJC5tNHMiIHN0YXJ0TnVtYmVyPSIxIj48L1NlZ21lbnRUZW1wbGF0ZT4KICAgICAgICA8QXVkaW9DaGFubmVsQ29uZmlndXJhdGlvbiBzY2hlbWVJZFVyaT0idXJuOm1wZWc6ZGFzaDoyMzAwMzozOmF1ZGlvX2NoYW5uZWxfY29uZmlndXJhdGlvbjoyMDExIiB2YWx1ZT0iMiI+PC9BdWRpb0NoYW5uZWxDb25maWd1cmF0aW9uPgogICAgICA8L1JlcHJlc2VudGF0aW9uPgogICAgPC9BZGFwdGF0aW9uU2V0PgogIDwvUGVyaW9kPgo8L01QRD4=",
  "playlistType": "application/dash+xml",
  "metadata": {
    "assetId": "",
    "baseUrls": [
      "https://fortnite-vod.akamaized.net/fVALLXBdAuxUVUnnQj/75f0daab-c8a5-4c83-9ea8-6b604b09d417/",
      "https://fortnite-vod.akamaized.net/fVALLXBdAuxUVUnnQj/75f0daab-c8a5-4c83-9ea8-6b604b09d417/"
    ],
    "supportsCaching": true,
    "ucp": "a",
    "version": "75f0daab-c8a5-4c83-9ea8-6b604b09d417"
  }
}
```