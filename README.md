# rumap-android-releases

Публичный репозиторий только для релизных артефактов и манифеста обновлений мобильного приложения **rumap-android** (канал `stable`). Исходный код приложения в этом репозитории не публикуется.

## Формат релизов

Каждый выпуск публикуется в GitHub Releases под тегом `vX.Y.Z` и содержит:

- `rumap-android-arm64-v8a.apk` — подписанный релизный APK для архитектуры `arm64-v8a`;
- `SHA256SUMS.txt` — контрольные суммы SHA-256 релизных артефактов.

Заметки к релизу задаются вручную и не генерируются автоматически из истории коммитов.

## Манифест автообновления (`updater`)

Актуальный манифест канала `stable` публикуется в rolling-релизе с тегом [`updater`](https://github.com/rumap/rumap-android-releases/releases/tag/updater):

- `https://github.com/rumap/rumap-android-releases/releases/download/updater/latest.json`

Схема `latest.json`:

```json
{
  "version": "0.1.0",
  "versionCode": 10099,
  "minVersionCode": 0,
  "notes": "...",
  "platforms": {
    "arm64-v8a": {
      "url": "https://github.com/rumap/rumap-android-releases/releases/download/v0.1.0/rumap-android-arm64-v8a.apk",
      "sha256": "...",
      "size": 12345678
    }
  }
}
```

## Проверка целостности (SHA-256)

После загрузки `rumap-android-arm64-v8a.apk` и `SHA256SUMS.txt` из соответствующего релиза проверьте контрольную сумму:

```sh
sha256sum -c SHA256SUMS.txt
```

Ожидаемый результат: `rumap-android-arm64-v8a.apk: OK`.
