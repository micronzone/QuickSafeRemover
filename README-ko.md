<p align="right">
  [한국어]
  [<a href="README.md">English</a>]
</p>

# qsrm

> 안전하고 빠른 대량 삭제 도구 – 실수로 인한 삭제를 방지하세요!

## 소개

`qsrm`은 파일 및 디렉토리를 목록 파일에서 안전하게 삭제하는 Bash 스크립트입니다. 기본은 **드라이런 모드**로 작동하며, 실제 삭제 여부를 사용자가 명확히 선택할 수 있도록 합니다.

- ✅ 기본은 삭제 미수행 (드라이런)
- ⚠️ 삭제 전 확인
- 🔐 목록 기반 삭제로 실수 방지
- 🧹 대량 삭제 자동화에 유용

## 설치

```bash
chmod +x qsrm
mv qsrm /usr/local/bin/
```

## 사용

```bash
qsrm [-f] [-r] path_list.txt
```

## 옵션

| Option | Description                          |
| ------ | ------------------------------------ |
| `-f`   | 강제 삭제 (삭제 전 확인 생략)    |
| `-r`   | 실제 삭제 수행 (기본은 Dry-run) |

## 예제

targets.txt 파일에 삭제할 경로들을 한 줄씩 작성합니다:

```bash
/tmp/test1
~/Downloads/old_project
```

실제 삭제 없이 미리 확인 (기본 모드):

```bash
qsrm targets.txt
```

삭제 전 확인 후 실제로 삭제:

```bash
qsrm -r targets.txt
```

확인 없이 강제 삭제:

```bash
qsrm -f -r targets.txt
```

## 출력 예시

```yaml
[2025-07-18 11:00:00] Loading paths from: targets.txt
Total targets: 3
Dry-run mode ON
[DRY-RUN] Would delete: /tmp/test1
[DRY-RUN] Would delete: /tmp/test2
...

--- Summary ---
Total  : 3
Deleted: 3
```

## 권장 사항

- 항상 -r 없이 먼저 실행해 확인 후 삭제하세요.
- rm -rf는 위험하므로 자동화 전에 충분히 테스트하십시오.

## 라이선스

MIT License