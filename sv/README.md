## 1.安装iconv ##

http://www.gnu.org/software/libiconv

## 2.复制libspeakerverify.so ##
`sudo cp libspeakerverify.so /usr/local/lib`

## 3.设置搜索路径 ##

`vi /etc/ld.so.conf`
加入
`/usr/local/lib`
运行
`ldconfig`

## 4.Compile ##

Compile C
`gcc sv_api.c -o AI_SV -L. -lspeakerverify -m64`

Compile so
`gcc sv_api.c sv_api.h -shared -o libsv.so -fPIC -L. -lspeakerverify -m64`
