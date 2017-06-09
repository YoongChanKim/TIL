PHP MYSQL Connect(PHP 데이터 베이스 연동)
=======================================
php의 데이터베이스 연결방식은 mysql_connect 와 myaqli_connect 두 가지있다.

## mysql_connect 방식(기존 방식)
<?
$db_host = "hostname";
$db_user = "root";
$db_passwd = "test1234";
$db_name = "test";

$connect = mysql_connect($db_host,$db_user,$db_passwd,$db_name);

mysql_select_db($db_name, $connect);
?>

## mysqli_connect 방식(새로운 방식)
<?php
$db_host = "hostname";
$db_user = "root";
$db_passwd = "test1234";
$db_name = "test";

$connect = mysqli_connect($db_host,$db_user,$db_passwd,$db_name);

if(mysqli_connect_errno($connect)) {
  echo "Failed" . mysqli_connect_errno();
}
?>

두 방법의 차이점은 mysqli 는 mysql에 비해 빠르고 안정적이며 보안이 더 잘되어 있다.
