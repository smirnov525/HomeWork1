# Домашняя работа № 1
## Установка ВМ

+ Развернута ВМ в ЯндексКлауд с 5 дисками по 1ГБ



## Создание RAID 5
+ Создаем RAID 5 командой  
<img width="839" alt="Снимок экрана 2023-10-15 в 17 18 26" src="https://github.com/smirnov525/HomeWork1/assets/138726354/759157c5-fa6b-4dd4-99e5-8ad3d736c2ec">

+ Проверяем, что RAID собрался нормально
<img width="847" alt="Снимок экрана 2023-10-15 в 17 28 23" src="https://github.com/smirnov525/HomeWork1/assets/138726354/88167b06-7988-4494-a024-cde2aad6fd1a">

## Сломать/Починить RAID

+ Ломаем диск sde командой mdadm /dev/md0 --fail /dev/sde
+ Проверяем, что диск зафейлился
<img width="716" alt="Снимок экрана 2023-10-15 в 17 58 50" src="https://github.com/smirnov525/HomeWork1/assets/138726354/8a13b1b8-40c1-4932-97c8-a99c790993c6">

+ Имитируем замену диска. Удалим диск из массива командой mdadm /dev/md0 --remove /dev/vde и добавим командой mdadm /dev/md0 --add /dev/vde

## Создать GPT раздел, пять партиций и смонтировать их на диск

+ Создаем раздел GPT на RAID командой arted -s /dev/md0 mklabel gpt
+ Создаем партиции 
