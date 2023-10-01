# AiLoaderInstaller
Установочный пакет и инструкция

## Files list:
- `AiLoader installer FULL.zip` - Набор Android SDK для всех ОС + содержимое набора LITE
- `AiLoader installer LITE.zip` - Установочный пакет и инструкция по установке
- `app-release.apk` - Установочный пакет
- `README.md` - Файл с информацией о репозитории и инструкцией по установке

> `Китайские антивирусы могут жаловаться на содержимое FULL версии`, рекомендуется отключить их на время работы или добавить папку с архивом в исключения на время работы

# Инструкция по установке AiLoader v10.2023

> - Аккуратно снимите коробку с планшетом со стены потащив ее вверх и после на себя
> - Извлеките поддерживающие балки сдвинув их в сторону и аккуратно вытащив с одной из сторон
>> Возможно балок будет 3, тогда центральную можно аккуратно повернуть, чтобы вытащить или установить на место
> - Вытащите частично планшет и отключите его от питания
> - Повесьте корпус на стену для удобства или отключите его от розетки, если есть такая возможность
>> Не оставляйте его висеть на кабеле питания

Для дальнейшей работы Вам понадобится ноутбук или любой другой компьютер на базе ОС Windows, Linux, Unix или MacOS с наличием рабочих USB портов

> - Перезагрузите планшет в fastboot (не путать в fastbootd!)
>> - Зажмите кнопку уменьшения громкости и кнопку питания до перехода планшета в режим fastboot (появится белый текст внизу слева на экране)
> Подключите планшет кабелем к компьютеру с установленным или распакованным ADB
>> - Необходимо в консоли перейти в папку с ADB перед началом работы
>>> ADB, fastboot и установочный пакет находятся в папке `platform-tools-{platform}`
>>> Папки для windows и linux соответственно

### Используйте команды:

> ##### Linux, Unix:
>
> `./fastboot oem off-mode-charge 0`
> `./fastboot reboot recovery`

> ##### Windows:
>
> <code>fastboot oem off-mode-charge 0<br/>fastboot reboot recovery</code>

Планшет будет перезагружен в recovery...

> После загрузки в Recovery необходимо сбросить планшет до заводских настроек (wipe/factory reset)
>> Истользуйте кнопки громкости для перемещения и кнопку питания для подтверждения
>> После сброса перезагрузите планшет в систему (reboot system)

> После загрузки планшета начните его настройку
>> После нажатия кнопки `Начать` пролистайте вниз и на мелком тексте нажмите на синее слово `здесь`
>> Отключите переключатель в появившемся окне и подтвердите действие
>> Вернитесь на предыдущий экран с помощью кнопок навигации и нажмите `Далее`
>>
>> Произведите `оффлайн настройку` планшета (оффлайн настройка `обязательна` даже при наличии какой либо связи)
>> Попутно `отключите` все галочки на странице с настройкой `геолокации`

> Как только станет доступен главный экран - `отключите передачу данных и подтвердите действие!`
>>> Позже данная функция будет включена автоматически при необходимости
>>> Это необходимо для сокращения расходов на автоматическую установку или обновление ненужных системных приложений, которые будут отключены в процессе установки
>> Также зайдите в настройки WiFi и подключитесь к самой стабильной точке, работающей как можно дольше, если таковая имеется
>>> Это необходимо, если на планшете до отключения передачи данных не было подключения к 3G или 4G или требовалась регистрация в сети

> После завершения настройки необходимо включить `отладку по USB` на устройстве
>> - Перейдите в `настройки системы`, откройте свойства системы и нажмите на версию Android
>> - Найдите строку `Номер сборки` и нажмите быстро на неё `7-10 раз`, пока не будет включен `режим разработчика`
>> - Вернитесь в `настройки системы` и перейдите в раздел `для разработчиков`
>> - Если экран в вертикальной ориентации, то скорее всего внизу экрана уже будет видна строчка включения `отладки по USB`
>> - Убедитесь что планшет `подключен к компьютеру кабелем`, включите `отладку по USB` и после подтверждения включения отладки `подтвердите подключение компьютера` предварительно `поставив галочку` в появившемся окне

Для удобства переместите `app-release.apk` в папку `platform-tools`, которую будете использовать для установки

> - Выйдите на `главный экран` и запустите следующие скрипты (можно скопировать весь текст и вставить в консоль для удобства):

> ПРЕДВАРИТЕЛЬНО `поместите APK файл` в папку с `ADB` или в `текущую рабочую папку` консоли в зависимости от настроек системы
>> Перед выполнением команд убедитесь, что планшет работает в `книжной ориентации`, а штекер кабеля находится снизу
>> Во время установки `препятствуйте отключению экрана`!
>> Также убедитесь, что `устройство подключено к компьютеру` и `работает с ADB`:
<code>./adb devices</code>

##### Linux, Unix:

<code>./adb shell locksettings set-disabled true
./adb shell pm disable-user com.android.fmradio
./adb shell pm disable-user com.google.android.youtube
./adb shell pm disable-user com.google.android.ext.services
./adb shell pm disable-user com.google.android.googlequicksearchbox
./adb shell pm disable-user com.google.android.apps.googleassistant
./adb shell pm disable-user com.lenovo.launcher.provider
./adb shell pm disable-user com.tblenovo.launcher
./adb shell pm disable-user com.google.android.apps.docs
./adb shell pm disable-user com.google.android.apps.maps
./adb shell pm disable-user com.google.android.apps.kids.home
./adb shell pm disable-user com.tblenovo.whatsnewclient
./adb shell pm disable-user com.google.android.videos
./adb shell pm disable-user com.google.android.apps.photos
./adb shell pm disable-user com.lenovo.screenassistant
./adb shell pm disable-user com.google.android.apps.youtube.kids
./adb shell pm disable-user com.google.android.apps.books
./adb shell pm disable-user com.tblenovo.lenovoruapps
./adb shell pm disable-user com.google.android.apps.youtube.music
./adb uninstall com.yandex.browser
./adb uninstall com.google.android.apps.nbu.files
./adb uninstall com.google.android.calculator
./adb uninstall ru.yandex.searchplugin
./adb uninstall com.tblenovo.soundrecorder
./adb shell pm disable-user com.android.vending
./adb shell pm disable-user com.lenovo.ota
./adb shell pm disable-user com.google.android.apps.mediahome.launcher
./adb shell svc data enable
./adb install ./app-release.apk
./adb shell dpm set-device-owner kz.aocorp.ailoader/.DevAdminReceiver</code>

##### Windows:

<code>adb shell locksettings set-disabled true
adb shell pm disable-user com.android.fmradio
adb shell pm disable-user com.google.android.youtube
adb shell pm disable-user com.google.android.ext.services
adb shell pm disable-user com.google.android.googlequicksearchbox
adb shell pm disable-user com.google.android.apps.googleassistant
adb shell pm disable-user com.lenovo.launcher.provider
adb shell pm disable-user com.tblenovo.launcher
adb shell pm disable-user com.google.android.apps.docs
adb shell pm disable-user com.google.android.apps.maps
adb shell pm disable-user com.google.android.apps.kids.home
adb shell pm disable-user com.tblenovo.whatsnewclient
adb shell pm disable-user com.google.android.videos
adb shell pm disable-user com.google.android.apps.photos
adb shell pm disable-user com.lenovo.screenassistant
adb shell pm disable-user com.google.android.apps.youtube.kids
adb shell pm disable-user com.google.android.apps.books
adb shell pm disable-user com.tblenovo.lenovoruapps
adb shell pm disable-user com.google.android.apps.youtube.music
adb uninstall com.yandex.browser
adb uninstall com.google.android.apps.nbu.files
adb uninstall com.google.android.calculator
adb uninstall ru.yandex.searchplugin
adb uninstall com.tblenovo.soundrecorder
adb shell pm disable-user com.android.vending
adb shell pm disable-user com.lenovo.ota
adb shell pm disable-user com.google.android.apps.mediahome.launcher
adb shell svc data enable
adb install ./app-release.apk
adb shell dpm set-device-owner kz.aocorp.ailoader/.DevAdminReceiver</code>


> Если в течении 2х минут на кране появилась надпись AiLoader и синяя кнопка - процесс установки и регистрации устройства прошел успешно
> В ином случае придется начать процедуру сначала
>> Возможно в устройстве отсутствует сим-карта или не подключен WiFi

> Если Вы видите AiLoader - [войдите](https://aipit.kz) в аккаунт школы на телефоне или ноутбуке с камерой
>	
>
>> - Зайдите в раздел AiLoader на телефоне или ноутбуке с камерой и включите удобную Вам камеру для сканирования кода с экрана планшета
>> - Нажмите на синюю кнопку и отсканируйте код
>>> У Вас на это будет 5 секунд, после чего страница будет обновлена
>
> Если код был успешно отсканирован - планшет автоматически войдет в систему под школьным аккаунтом и система станет доступна

Теперь планшет можно установить на место\
Не забудьте подключить питание и вставить все поддерживающие балки

---

https://emn178.github.io/online-tools/sha256_checksum.html
