objdump
=======
GNU 바이너리 유틸리티의 일부로서, 라이브러리, 컴파일된 오브젝트 모듈, 공유 오브젝트 파일, 독립 실행 파일 등의 바이너리 파일들의 정보를 보여주는 프로그램이다. objdump는 elf 파일을 어셈블리어로 보여주는 디스어셈블리어로 보여주는 디스어셈블러로 사용 될 수 있다.

## 사용법

```
objdump [-d][-S][-l][obj 파일명] > [output 파일명]
```

### 옵션

* -d : disassemble, 어셈블리어 코드 목록을 생성

* -S : 소스코드를 최대한 보여주는 옵션, optimization된 object file의 경우 소스코드가 모두 보이지 않을 수 있음

* -l : 소스코드에서 line을 보여주는 옵션

* >[output 파일명] : 파일명으로 export 하게된다. 생략하면 화면에 즉시 출력됨

### 다른 옵션들

```
objdump [-a|--archive-headers]

        [-b bfdname|--target=bfdname]
        [-C|--demangle[=style] ]
        [-d|--disassemble]
        [-D|--disassemble-all]
        [-z|--disassemble-zeroes]
        [-EB|-EL|--endian={big | little }]
        [-f|--file-headers]
        [--file-start-context]
        [-g|--debugging]
        [-h|--section-headers|--headers]
        [-i|--info]
        [-j section|--section=section]
        [-l|--line-numbers]
        [-S|--source]
        [-m machine|--architecture=machine]
        [-M options|--disassembler-options=options]
        [-p|--private-headers]
        [-r|--reloc]
        [-R|--dynamic-reloc]
        [-s|--full-contents]
        [-G|--stabs]
        [-t|--syms]
        [-T|--dynamic-syms]
        [-x|--all-headers]
        [-w|--wide]
        [--start-address=address]
        [--stop-address=address]
        [--prefix-addresses]
        [--[no-]show-raw-insn]
        [--adjust-vma=offset]
        [-V|--version]
        [-H|--help]
        objfile...  
```

출처: http://log1.tistory.com/3 [log 1]
