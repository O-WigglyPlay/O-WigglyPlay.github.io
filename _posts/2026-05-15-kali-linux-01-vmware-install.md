---
title: '[Kali Linux 01] VMware에 칼리 리눅스 설치 및 한글 설정'
excerpt: 'VMware 설치부터 Kali ISO 다운로드, VM 생성, 설치, 칼리리눅스 초기 설정까지'

categories:
    - 정보보안
tags:
    - [Kali, Linux, VMware, 설치, 정보보안, 가상머신]

permalink: /security/kali-linux-01-vmware-install/

toc: true
toc_sticky: true

date: 2026-05-15
last_modified_at: 2026-05-15
---

## Kali Linux 시리즈 — 1장: 설치

이번 글은 **칼리 리눅스를 VMware 가상머신에 올리는 과정**만 다룹니다.  
도구 사용법, 네트워크 스캔, 침투 테스트 실습은 이후 이어서 정리할 예정입니다.

---

## Kali Linux란?

**Kali Linux**는 Debian 기반의 **보안·침투 테스트용 배포판**입니다.  
Nmap, Wireshark, Metasploit 등 보안 도구가 많이 포함되어 있어, **합법적인 범위 안에서** 학습,진단,허가된 테스트에 사용합니다.

> **주의:** 본인 소유,허가받은 시스템,연습용 가상 환경에서만 사용하세요. 무단 스캔,침입은 법적 문제가 될 수 있습니다.

---

## 준비물

| 항목        | 권장                                               |
| ----------- | -------------------------------------------------- |
| 호스트 OS   | Windows 10/11 또는 macOS                           |
| VMware      | Workstation Player(Windows) / Fusion Player(macOS) |
| 가상 디스크 | **40GB 이상**                                      |
| 가상 메모리 | **4GB 이상** (호스트 RAM 8GB 이상 권장)            |

---

## VMware 설치

필자는 macOS 환경에서 설치했으므로 macOS 기준으로 설명한다.

### macOS — VMware Fusion Player

1. [BroadCom](https://profile.broadcom.com/web/registration)에서 회원가입 진행
2. [BroadCom Download](https://support.broadcom.com/group/ecx/downloads)에서 아래 사진과 같이 진행
   ![VMware Fusion 설치](/assets/images/posts_img/kali-linux-01/vmware설치.png)
3. Here 누른 후 아래와 같이 진행
   ![VMware Fusion 설치](/assets/images/posts_img/kali-linux-01/vmware설치2.png)
4. 제일 최신 버전 설치
5. 다운로드를 누르려고 하면 바로 진행이 안 되고 인증을 받아야하는데 이쪽에서 필자는 많이 실수했다. 필자는 이미 진행해서 안 뜨지만 아래 사진과 같은 부분에 아마 링크가 있고 해당 링크 타고 들어가면 체크박스를 체크할 수 있게 풀리게 될거다.
   ![BroadCom 권한 인증](/assets/images/posts_img/kali-linux-01/vmware설치3.png)
6. 체크박스를 누르고는 아래처럼 그냥 다운로드하면 된다.
   ![VMware Fusion 설치](/assets/images/posts_img/kali-linux-01/vmware설치4.png)

---

## Kali ISO 다운로드

1. [Get Kali](https://www.kali.org/get-kali/#kali-installer-images) 접속
2. 본인한테 맞는 설치버전 확인
3. 아래 사진 참고해서 iso파일 설치
   ![kali linux 설치](/assets/images/posts_img/kali-linux-01/kali설치.png)

## VMware에 가상머신 만들기

### 1. 새 VM 생성

1. VMware 실행 → **Create a New Virtual Machine** (또는 **새 가상 시스템 만들기**)
2. **Installer disc image file (iso)** 선택 → 다운받은 **Kali ISO** 지정
3. 게스트 OS: **Linux → Debian 64-bit**
4. **Virtual machine name:** `Kali-Linux` (원하는 이름)
5. **Disk size:** **40GB 이상**, **Store virtual disk as a single file** 권장 (필자는 80GB)
6. **Customize Hardware** (하드웨어 사용자 지정)에서 아래 확인 후 **Finish**

| 설정       | 권장 값         |
| ---------- | --------------- |
| Memory     | 4096 MB 이상    |
| Processors | 2코어 이상      |
| CD/DVD     | Kali ISO 연결됨 |

---

## Kali 설치 (Graphical install)

1. VM **Power On** → 부팅 메뉴에서 방향키를 이용해 **Graphical install** 선택 후 엔터
2. **언어 / 지역 / 키보드** 설정 (한국어 가능)
3. **호스트명:** 예) `kali`
4. **도메인명:** .com
5. **사용자 계정**
    - 일반 사용자 이름·비밀번호 (매일 로그인용)
    - **root 비밀번호** 별도 설정
6. **디스크 분할:** 전부 다 기본
7. **소프트웨어 선택:** 기본 제외 추가 필요한 프로그램있으면 체크 후 다음
8. 설치 기다린 후 완료

---

## 설치 직후 설정

### 1. 시스템 업데이트

**터미널에서 암호를 작성할때는 비밀번호를 적어도 시각적으로는 보이지 않지만 실제로는 작동중이니 비밀번호 적고 엔터 치면 넘어가진다.**

터미널에서:

```bash
sudo apt update
sudo apt full-upgrade -y
```

재부팅이 필요하면:

```bash
sudo reboot
```

### 2. 한글 깨짐 현상 수정 (필요에따라 진행)

설치 시 한국어를 선택했는데도, 터미널, 파일, 이름 등 한글이 깨져보일 수 있다.
아래 명령어를 따라한 후 재부팅 하면 대부분 해결 될 것이다.

```bash
sudo apt update
sudo apt install -y locales fonts-nanum
sudo reboot
```

(선택) 한글 입력이 필요할 때

```bash
sudo apt install -y ibus ibus-hangul
ibus-setup
```

설정 후 재부팅 후 확인.

### 3. 동작 확인

```bash
uname -a
cat /etc/os-release
which nmap
```

Kali 버전 정보와 `nmap` 경로가 나오면 기본 환경은 준비된 것이다.

---
