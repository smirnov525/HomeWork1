# Домашняя работа № 1
## Установка ВМ

+ Развернута ВМ в ЯндексКлауд с 5 дисками по 1ГБ


## Создание RAID 5
+ Создаем RAID 5 командой  
![Альтернативный текст](https://cloud.mail.ru/public/foTa/1Nsze9fSC)
+ Проверяем, что RAID собрался нормально
![Альтернативный текст](https://cloud.mail.ru/public/ZXdB/JeF6Gm7jJ)

## Сломать/Починить RAID

+ Ломаем диск sde командой mdadm /dev/md0 --fail /dev/sde
+ Проверяем, что диск зафейлился
![Альтернативный текст](http://images.vfl.ru/ii/1628425083/cdbeab57/35427044.png)
+ Имитируем замену жесткого диска. Удалим “сломанный” диск из массива командой mdadm /dev/md0 --remove /dev/sde и добавим заново командой mdadm /dev/md0 --add /dev/sde

## Создать GPT раздел, пять партиций и смонтировать их на диск

+ Создаем раздел GPT на RAID командой arted -s /dev/md0 mklabel gpt
+ Создаем партиции 
