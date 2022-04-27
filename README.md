# PeacheperoLang

PeacheperoLang está basado en PHP, pero con una sintaxis mejorada y adaptada a
las necesidades y capacidades de @MarcosBL.

### Compilando PeacheperoLang

Para compilar PeacheperoLang necesitas instalar las siguientes cosas:

    sudo apt install -y pkg-config build-essential autoconf bison re2c \
                        libxml2-dev libsqlite3-dev libreadline-dev

Generar configuración:

    ./buildconf --force
    ./configure --with-readline --disable-phar

Compilar PeacheperoLang:

    make -j8

## Instalando PeacheperoLang

    make install

## Probando PeacheperoLang

    ./sapi/cli/php -a


## Cambios respecto a PHP

```
include      -> padentro
include_once -> padentro_una_vez
eval         -> ñapa
echo         -> ver
print        -> el_otro_ver
if           -> tal_vez
elseif       -> y_sino
else         -> y_si_no_ha_sido_nada_de_eso
continue     -> circulen
break        -> quietoooo
function     -> plato_de_espagueti
class        -> olla_de_espagueti
namespace    -> cocina
return       -> devolver
try          -> esto_va_a_cascar
catch        -> efectivamente_ha_cascado
finally      -> y_para_terminar_el_apaño
while        -> dar_vueltas
var          -> variable
empty        -> es_saldo_de_mi_cuenta_bancaria
extends      -> no_usar_peligro
enum         -> lista_de_cosas
exit         -> marcho_que_teño_que_marchar
foreach      -> pito_pito_gorgorito
throw        -> a_tomar_por_culo
```

## Ejemplos

```
$ ./sapi/cli/php -a
php > $res = ñapa('return 2+2;');
php > ver $res;
4
php > tal_vez($a == "adios") {
        el_otro_ver("es hola!");
      } y_si_no_ha_sido_nada_de_eso {
        ver("no es hola, es otra cosa");
      }
no es hola, es otra cosa
php >
php > marcho_que_teño_que_marchar
$
```


## Para mejorar PeacheperoLang

Modificar el parser:

```
Zend/zend_language_parser.y
Zend/zend_language_scanner.l
```

Limpiar antes de compilar de nuevo:

```
make clean
rm Zend/zend_language_parser.c
rm Zend/zend_language_parser.h
rm Zend/zend_language_scanner.c
```
