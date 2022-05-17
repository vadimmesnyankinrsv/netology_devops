# Описание .gitignore из каталога terraform

Добавленный в каталог terraform .gitignore позволит git'у в будущем проигнорировать следующите файлы:

* все директории и их субдирректории .terraform во всех субдиректориях
* файлы заканчивающиеся на .tfstate и .tfstate.ЧТО_ТО_ЕЩЕ  
* файлы crash.log и файлы вида crash.ЧТО_ТО.log
* файлы, имена которых заканчиваются на .tfvars и .tfvars.json
* файлы override.tf, override.tf.json и файлы, имена которых заканчиваются на _override.tf или _override.tf.json
* файлы .terraformrc и terraform.rc