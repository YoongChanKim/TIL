Raspberry Pi 고정아이피 할당
===========================

1. 설정 경로

```
$sudo vi /etc/dhcpcd.conf
```

2. 이더넷 고정아이피 설정
```
interface eth0
static ip_address=192.168.xxx.xxx/24
```

__x로 되어 있는 부분은 임의의 값을 넣는다. 또한 168.다음에 올 숫자는 동일해야 접속이 가능하다.__
