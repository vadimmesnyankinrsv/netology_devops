# Домашнее задание к занятию «2.4. Инструменты Git»

### 1. Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.

    git show aefea

aefead2207ef7e2aa5dc81a34aedf0cad4c32545

Update CHANGELOG.md

### 2. Какому тегу соответствует коммит 85024d3?

    it log 85024d3 -1

v0.12.23

### 3. Сколько родителей у коммита b8d720? Напишите их хеши.

    git rev-list --parents -n 1 b8d720

Это merge коммит, у него два родителя - 56cd7859e и 9ea88f22f

### 4. Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24.

    git log --oneline "v0.12.23~1".."v0.12.24"

* **b14b74c49** [Website] vmc provider links
* **3f235065b** Update CHANGELOG.md
* **6ae64e247** registry: Fix panic when server is unreachable
* **5c619ca1b** website: Remove links to the getting started guide's old location
* **06275647e** Update CHANGELOG.md
* **d5f9411f5** command: Fix bug when using terraform login on Windows
* **4b6d06cc5** Update CHANGELOG.md
* **dd01a3507** Update CHANGELOG.md
* **225466bc3** Cleanup after v0.12.23 release

### 5. Найдите коммит в котором была создана функция func providerSource, ее определение в коде выглядит так func providerSource(...) (вместо троеточего перечислены аргументы).

    git log --oneline -S "func providerSource("

**8c928e835** main: Consult local directories as potential mirrors of providers

### 6. Найдите все коммиты в которых была изменена функция globalPluginDirs.

    git grep -p "func globalPluginDirs("
    git log -L :globalPluginDirs:plugins.go

* **78b12205587fe839f10d946ea3fdc06719decb05** Remove config.go and update things using its aliases
* **52dbf94834cb970b510f2fba853a5b49ad9b1a46** keep .terraform.d/plugins for discovery
* **41ab0aef7a0fe030e84018973a64135b11abcd70** Add missing OS_ARCH dir to global plugin paths
* **66ebff90cdfaa6938f26f908c7ebad8d547fea17** move some more plugin search path logic to command
* **8364383c359a6b738a436d1b7745ccdce178df47** Push plugin discovery down into command package

### 7. Кто автор функции synchronizedWriters?

    git log --oneline -S "func synchronizedWriters("
    git show 5ac311e2a

Martin Atkins <mart@degeneration.co.uk>