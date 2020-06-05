## Laboratory work I

<a href="https://yandex.ru/efir/?stream_id=vsVJzkz4i9-s"><img src="https://raw.githubusercontent.com/tp-labs/lab01/master/preview.png" width="640"/></a>

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [x] 1. Ознакомиться со ссылками учебного материала
- [x] 2. Выполнить инструкцию учебного материала
- [x] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```bash
$ export GITHUB_USERNAME=gnole
$ export GIST_TOKEN=*******************************
```

```sh
$ mkdir -p ${GITHUB_USERNAME}/workspace
$ cd ${GITHUB_USERNAME}/workspace
$ cd ..
$ pwd /home/ivan
```

```sh
$ mkdir -p workspace/tasks/
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
$ cd workspace
```

```sh
# Debian
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz# загружаем с помощью утилиты wget пакет nodej
$ tar -xf node-v6.11.5-linux-x64.tar.xz
$ rm -rf node-v6.11.5-linux-x64.tar.xz
$ mv node-v6.11.5-linux-x64 node
```

```sh
$ ls node/bin
$ echo ${PATH} /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
$ export PATH=${PATH}:`pwd`/node/bin
$ echo ${PATH} /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/home/ivan/workspace/node/bin
$ mkdir scripts
$ cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
$ source scripts/activate
```

```sh
$ gem install gist
Successfully installed gist-5.1.0
Parsing documentation for gist-5.1.0
Done installing documentation for gist after 0 seconds
1 gem installed

```sh
$ (umask 0077 && echo ${GIST_TOKEN} > ~/.gist)
```

## Report

```sh
$ export LAB_NUMBER=01
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gist REPORT.md
```

## Homework

[x] 1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.

[x] 2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`

[x] 3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.

[x] 4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.

[x] 5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).

[x] 6. Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.

[x] 7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.

[x] 8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).

[x] 9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.

[x] 10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.

[x] 11. Найдите *топ10* самых "тяжёлых".

```
#Homework
sh
wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
```
```
sh
$ tar -xf boost_1_69_0.tar.gz # распаковываем архив
$ cd boost_1_69_0 
$ pwd
/home/ivan/workspace/reports/lab01/boost_1_69_0
$ ls -f . | wc -l # Считаем количество файлов в **boost**
20
$ find . -type f | wc -l 
61191
$ find . -type f -name '*.h' | wc -l # Находим все файлы с расширением '*.h' (заголовочный файл)
296 
$ find . -type f -name '*.cpp' | wc -l  # Находим все файлы с расширением '*.сpp' (файл C++)
13774
$ find . -type f '!' -name '*.cpp' -a '!' -name '*.cpp' | wc -l # Находим все остальные файлы
47121
```
```
sh
$ find . -type f -name 'any.hpp' # Полный путь до файла 'any.hpp' 
./boost/any.hpp
./boost/fusion/algorithm/query/any.hpp
./boost/fusion/algorithm/query/detail/any.hpp
./boost/fusion/include/any.hpp
./boost/hana/any.hpp
./boost/hana/fwd/any.hpp
./boost/proto/detail/any.hpp
./boost/spirit/home/support/algorithm/any.hpp
./boost/type_erasure/any.hpp
./boost/xpressive/detail/utility/any.hpp
```
```
sh
boot_1_69_0/boost/asio/async_result.hpp
...
boost_1_69_0/doc/html/process/reference.html
mv boost_1_69_0/=boost_output/lib/ boost-libs/

mv boost_1_69_0/=boost_output/lib/ boost-libs/# Перенесем статические библиотеки в директорию ~/boost-libs
```
```
sh
$ find . type -f -exec du -h {} +; # дисковое пространство файла 
100K ./libboost_stacktrace_basic.a
2,4M ./libboost_wave.dylib
7,8M ./libboost_math_tr1.a
5,4M ./libboost_python27.a 164K ./libboost_thread.dylib 100K ./libboost_math_c99f.dylib
480K ./libboost_$
1,9M ./libboost_math_c99f.a
1,8M ./libboost_math_c99l.a
1,3M ./libboost_iostreams.a
1,1M ./libboost_thread.a
7,3M ./libboost_program_options.a
188K ./libboost_iostreams.dylib
300K ./libboost_coroutine.a
276K ./libboost_timer.a
412K ./libboost_wserialization.dylib 940K ./libboost_contract.a
172K ./libboost_contract.dylib 892K ./libboost_numpy27.a
740K ./libboost_type_erasure.a
21M ./libboost_log_setup.a
16K ./libboost_atomic.a
208K ./libboost_random.a
104K ./libboost_prg_exec_monitor.dylib 528K ./libboost_date_time.a
648K ./libboost_graph.dylib
828K ./libboost_locale.dylib
```
```
sh
$ find . type -f -exec du -h {} +|sort -rh | head -n 10  # mon10 самых "тяжёлых"
./libboost_log-vc141-mt-gd-x32-1_70.lib
./libboost_log-vc141-mt-gd-x64-1_70.lib
./libboost_log_setup-vc141-mt-gd-x32-1_70.lib
./libboost_log_setup-vc141-mt-gd-x64-1_70.lib
./libboost_regex-vc141-mt-gd-x64-1_70.lib
./libboost_test_exec_monitor-vc141-mt-gd-x32-1_70.lib
./libboost_test_exec_monitor-vc141-mt-gd-x64-1_70.lib
./libboost_unit_test_framework-vc141-mt-gd-x64-1_70.lib
./libboost_wave-vc141-mt-gd-x32-1_70.lib
./libboost_wave-vc141-mt-gd-x64-1_70.lib

```
Copyright (c) 2015-2020 The ISC Authors
```
