# О плагине
Является доработанной версией встроенного плагина Yandex TTS, позволяющий работать с новой версией TTS от Яндекс.Облака, в том числе с новыми премиум-голосами которые используются в помощнике Алисе.

# Установка и настройка
Для установки поместить папку yandexcloudtts в /usr/share/hassio/homeassistant/custom_components и прописать в конфигурацию Home Assistant:

```yaml
tts:
  - platform: yandexcloudtts
    api_key: key
    language: ru-RU
    voice: alena
    codec: oggopus
```

Для получения API ключа:
1. Необходимо [зарегистрироваться](https://console.cloud.yandex.ru/) в сервисе Яндекс.Облако и подключить платный аккаунт.
2. Получить API ключ по [инструкции](http://https//cloud.yandex.ru/docs/iam/operations/api-key/create).

[Список голосов](https://cloud.yandex.ru/docs/speechkit/tts/voices) возможных к использованию.

# Использование
Вы можете использовать сервис tts.yandexcloudtts_say для синтеза речи.

```yaml
service: tts.yandexcloudtts_say
      entity_id: media_player.google_home
      message: "Пример"
```