# TiMP-Shamshetdinov lab01
Домашнее задание группы ИУ8Ц-41 Шамшетдинова Эмиля
1.Скачайте библиотеку boost с помощью утилиты wget. Адрес для скачивания https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz.

$ <wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz> 
<--2025-02-27 23:59:53--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
Resolving sourceforge.net (sourceforge.net)... 104.18.12.149, 104.18.13.149, 2606:4700::6812:d95, ...
Connecting to sourceforge.net (sourceforge.net)|104.18.12.149|:443... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/ [following]
--2025-02-27 23:59:54--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/
Reusing existing connection to sourceforge.net:443.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download [following]
--2025-02-27 23:59:54--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download
Reusing existing connection to sourceforge.net:443.
HTTP request sent, awaiting response... 302 Found
Location: https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABnwNJKOFWEc1TpCNK41UMktqgLS4Px1OF_33jKD6COKKamPiGz4KiO60eL2GXcLtJuybyxVsi0IOCxcfBqlY1Ua-H9ew%3D%3D&use_mirror=unlimited&r= [following]
--2025-02-27 23:59:55--  https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABnwNJKOFWEc1TpCNK41UMktqgLS4Px1OF_33jKD6COKKamPiGz4KiO60eL2GXcLtJuybyxVsi0IOCxcfBqlY1Ua-H9ew%3D%3D&use_mirror=unlimited&r=
Resolving downloads.sourceforge.net (downloads.sourceforge.net)... 104.18.13.149, 104.18.12.149, 2606:4700::6812:c95, ...
Connecting to downloads.sourceforge.net (downloads.sourceforge.net)|104.18.13.149|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://unlimited.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1 [following]
--2025-02-27 23:59:56--  https://unlimited.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1
Resolving unlimited.dl.sourceforge.net (unlimited.dl.sourceforge.net)... 185.119.90.247
Connecting to unlimited.dl.sourceforge.net (unlimited.dl.sourceforge.net)|185.119.90.247|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 111710205 (107M) [application/x-gzip]
Saving to: ‘boost_1_69_0.tar.gz’

boost_1_69_0.tar.gz 100%[================>] 106.53M  5.13MB/s    in 23s     

2025-02-28 00:00:19 (4.72 MB/s) - ‘boost_1_69_0.tar.gz’ saved [111710205/111710205]>

2.Разархивируйте скаченный файл в директорию ~/boost_1_69_0

$ <mkdir ~boost_1_69_0>
<>
$ <tar -xzf boost_1_69_0.tar.gz>
<>

3.Подсчитайте количество файлов в директории ~/boost_1_69_0 не включая вложенные директории.
(Ввод)

$ <find ~/boost_1_69_0 -maxdepth 1 -type f | wc -l>
<12>

4.Подсчитайте количество файлов в директории ~/boost_1_69_0 включая вложенные директории.

$ <find ~/boost_1_69_0 -type f | wc -l  >
<61191>

5.Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp).

$ <header_files=$(find ~/boost_1_69_0 -type f -name "*.hpp" | wc -l)>
<>
$ <cpp_files=$(find ~/boost_1_69_0 -type f -name "*cpp" |wc -l)>
<>
$ <other_files=$(find ~/boost_1_69_0 -type f ! -name "*.hpp" ! -name "*cpp.">
<>
$ <echo "Header files: $header_files">
<Header files: 14912>
$ <echo "CPP files: $cpp_files" >
<CPP files: 13774>
$ <echo "Other files: $other_files">
<Other files: 46279>

6.Найдите полный пусть до файла any.hpp внутри библиотеки boost.

$ <find ~/boost_1_69_0 -name "any.hpp">
</home/shamshetdinov/boost_1_69_0/boost/type_erasure/any.hpp
/home/shamshetdinov/boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
/home/shamshetdinov/boost_1_69_0/boost/fusion/algorithm/query/any.hpp
/home/shamshetdinov/boost_1_69_0/boost/fusion/include/any.hpp
/home/shamshetdinov/boost_1_69_0/boost/xpressive/detail/utility/any.hpp
/home/shamshetdinov/boost_1_69_0/boost/any.hpp
/home/shamshetdinov/boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
/home/shamshetdinov/boost_1_69_0/boost/proto/detail/any.hpp
/home/shamshetdinov/boost_1_69_0/boost/hana/any.hpp
/home/shamshetdinov/boost_1_69_0/boost/hana/fwd/any.hpp>

7.Выведите в консоль все файлы, где упоминается последовательность boost::asio.

$ <grep -rl "boost::asio" ~/boost_1_69_0>
</home/shamshetdinov/boost_1_69_0/boost/asio/serial_port.hpp
/home/shamshetdinov/boost_1_69_0/boost/asio/buffered_write_stream.hpp
/home/shamshetdinov/boost_1_69_0/boost/asio/ts/netfwd.hpp
/home/shamshetdinov/boost_1_69_0/boost/asio/local/datagram_protocol.hpp
/home/shamshetdinov/boost_1_69_0/boost/asio/local/stream_protocol.hpp> //Представил небольшой фрагмент вывода: так как исходный текст слишком большой ддля вставки.

8.Скомпилирутйе boost. Можно воспользоваться инструкцией или ссылкой.

$ <cd ~/boost_1_69_0>
<>
$ <./bootstrap.sh>
<Building Boost.Build engine with toolset gcc... tools/build/src/engine/bin.linuxarm/b2
Detecting Python version... 3.12
Detecting Python root... /usr
Unicode/ICU support for Boost.Regex?... /usr
Generating Boost.Build configuration in project-config.jam...

Bootstrapping is done. To build, run:

    ./b2
    
To adjust configuration, edit 'project-config.jam'.
Further information:

   - Command line help:
     ./b2 --help
     
   - Getting started guide: 
     http://www.boost.org/more/getting_started/unix-variants.html
     
   - Boost.Build documentation:
     http://www.boost.org/build/doc/html/index.html>
$ <./b2 -j4> //'-j4' использовал для многопоточной сборки с целью сокращения сборки
<Performing configuration checks

    - default address-model    : 64-bit
    - default architecture     : arm

Building the Boost C++ Libraries.


    - C++11 mutex              : yes
    - lockfree boost::atomic_flag : yes
    - Boost.Config Feature Check: cxx11_auto_declarations : yes
    - Boost.Config Feature Check: cxx11_constexpr : yes
    - Boost.Config Feature Check: cxx11_defaulted_functions : yes> //Представил небольшой фрагмент вывода: так как исходный текст слишком большой ддля вставки.
$ <ls bin.v2/libs/> //Проверка сборки
<atomic     contract   filesystem  math            serialization  timer
chrono     coroutine  graph       program_options  stacktrace     type_erasure
config     date_time  iostreams   python           system         wave
container  exception  locale      random           test
context    fiber      log         regex            thread                     >
$ <sudo ./b2 install>
<[sudo] password for shamshetdinov:>
<Performing configuration checks

    - default address-model    : 64-bit (cached)
    - default architecture     : arm (cached)
    - C++11 mutex              : yes (cached)
    - lockfree boost::atomic_flag : yes (cached)
    - Boost.Config Feature Check: cxx11_auto_declarations : yes (cached)
    - Boost.Config Feature Check: cxx11_constexpr : yes (cached)
    - Boost.Config Feature Check: cxx11_defaulted_functions : yes (cached)> //Представил небольшой фрагмент вывода: так как исходный текст слишком большой ддля вставки
$ <echo $?> //Проверка статуса завершения сборки
<0>         //Статус подтверждён

9.Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.

$ <mkdir ~/boost-libs>
<>
$ <cp stage/lib/*.a ~/boost-libs/>
<>
$ <ls ~/boost-libs>   //Проверка новой директории
<libboost_atomic.a     libboost_math_c99.a         libboost_stacktrace_addr2line.a
libboost_chrono.a      libboost_math_c99f.a         libboost_stacktrace_backtrace.a
libboost_container.a   libboost_math_c99l.a         libboost_stacktrace_basic.a
libboost_context.a     libboost_math_tr1.a          libboost_stacktrace_noop.a
libboost_contract.a    libboost_math_tr1f.a         libboost_system.a
libboost_date_time.a   libboost_math_tr1l.a         libboost_test_exec_monitor.a
libboost_exception.a   libboost_prg_exec_monitor.a  libboost_timer.a
libboost_fiber.a       libboost_program_options.a   libboost_unit_test_framework.a
libboost_filesystem.a  libboost_random.a            libboost_wave.a
libboost_graph.a       libboost_regex.a             libboost_wserialization.a
libboost_iostreams.a   libboost_serialization.a                                      >

10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.

$ <du -h ~/boost-libs/*>
<4.0K    /home/shamshetdinov/boost-libs/libboost_atomic.a
264K    /home/shamshetdinov/boost-libs/libboost_chrono.a
148K    /home/shamshetdinov/boost-libs/libboost_container.a
24K     /home/shamshetdinov/boost-libs/libboost_context.a
364K    /home/shamshetdinov/boost-libs/libboost_contract.a
160K    /home/shamshetdinov/boost-libs/libboost_date_time.a
4.0K    /home/shamshetdinov/boost-libs/libboost_exception.a
240K    /home/shamshetdinov/boost-libs/libboost_fiber.a
424K    /home/shamshetdinov/boost-libs/libboost_filesystem.a
884K    /home/shamshetdinov/boost-libs/libboost_graph.a
296K    /home/shamshetdinov/boost-libs/libboost_iostreams.a
828K    /home/shamshetdinov/boost-libs/libboost_math_c99.a
568K    /home/shamshetdinov/boost-libs/libboost_math_c99f.a
760K    /home/shamshetdinov/boost-libs/libboost_math_c99l.a
3.7M    /home/shamshetdinov/boost-libs/libboost_math_tr1.a
2.9M    /home/shamshetdinov/boost-libs/libboost_math_tr1f.a
3.4M    /home/shamshetdinov/boost-libs/libboost_math_tr1l.a
224K    /home/shamshetdinov/boost-libs/libboost_prg_exec_monitor.a
1.6M    /home/shamshetdinov/boost-libs/libboost_program_options.a
92K     /home/shamshetdinov/boost-libs/libboost_random.a
3.1M    /home/shamshetdinov/boost-libs/libboost_regex.a
1.3M    /home/shamshetdinov/boost-libs/libboost_serialization.a
32K     /home/shamshetdinov/boost-libs/libboost_stacktrace_addr2line.a
20K     /home/shamshetdinov/boost-libs/libboost_stacktrace_backtrace.a
12K     /home/shamshetdinov/boost-libs/libboost_stacktrace_basic.a
4.0K    /home/shamshetdinov/boost-libs/libboost_stacktrace_noop.a
4.0K    /home/shamshetdinov/boost-libs/libboost_system.a
2.3M    /home/shamshetdinov/boost-libs/libboost_test_exec_monitor.a
56K     /home/shamshetdinov/boost-libs/libboost_timer.a
2.3M    /home/shamshetdinov/boost-libs/libboost_unit_test_framework.a
4.7M    /home/shamshetdinov/boost-libs/libboost_wave.a
812K    /home/shamshetdinov/boost-libs/libboost_wserialization.a>

11. Найдите топ10 самых "тяжёлых".

$ <du -h ~/boost-libs/* | sort -hr | head -n 10>
<4.7M    /home/shamshetdinov/boost-libs/libboost_wave.a
3.7M    /home/shamshetdinov/boost-libs/libboost_math_tr1.a
3.4M    /home/shamshetdinov/boost-libs/libboost_math_tr1l.a
3.1M    /home/shamshetdinov/boost-libs/libboost_regex.a
2.9M    /home/shamshetdinov/boost-libs/libboost_math_tr1f.a
2.3M    /home/shamshetdinov/boost-libs/libboost_unit_test_framework.a
2.3M    /home/shamshetdinov/boost-libs/libboost_test_exec_monitor.a
1.6M    /home/shamshetdinov/boost-libs/libboost_program_options.a
1.3M    /home/shamshetdinov/boost-libs/libboost_serialization.a
884K    /home/shamshetdinov/boost-libs/libboost_graph.a>
