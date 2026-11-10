<div align="center">

<img src="https://avatars.githubusercontent.com/u/311857797?v=4" width="120" alt="VOID logo"/>

<h1>VOID</h1>

<p><strong>WhiteHat School 4기 보안 연구팀</strong></p>

[![Team](https://img.shields.io/badge/Team-WhiteHat_School_4기_VOID-black)](https://github.com/VOID-wh4)
[![Focus](https://img.shields.io/badge/Focus-AV%2FEDR_Bypass_Research-red)](https://github.com/VOID-wh4)
[![Platform](https://img.shields.io/badge/Platform-Windows_x64-0078D6?logo=windows&logoColor=white)](https://github.com/VOID-wh4)

</div>

---

상용 안티바이러스 및 EDR 제품군의 탐지 특성을 분석하고, 우회 기법의 동작 원리를 연구합니다.  
Quasar RAT v1.4.1과 Mimikatz를 대상으로 페이로드 인코딩, 메모리 로딩, 프로세스 인젝션, 후킹 기법을 직접 구현·실험한 결과물을 공유합니다.

> 모든 연구는 승인된 격리 환경에서 수행되었습니다.

---

## 레포지토리

### 🛡️ [bypass](https://github.com/VOID-wh4/bypass)

AV/EDR 탐지 우회 기법 구현 모음.  
프로세스 인젝션, 후킹 우회, PE 로딩, 패킹 등 14개 모듈을 포함합니다.

| 카테고리 | 주요 기법 |
|---|---|
| 프로세스 인젝션 | APC Injection, Process Hollowing, Ghost Injection, Section Loader |
| 후킹 우회 | ntdll 언훅킹, AMSI Hooking (Detours/Frida) |
| PE 로딩 | Manual PE Mapper, In-Memory .NET Loader, PE-DLL Loader |
| 패킹 / 난독화 | MBAPacker, dotnetXorPacker, IPv4Fuscation |

**탐지 결과 (Quasar RAT 기준, 일부)**

| 기법 | Defender | Bitdefender | Kaspersky | nProtect |
|---|:---:|:---:|:---:|:---:|
| APC Injection | X | X | X | O |
| Manual PE Mapper | O | X | O | O |
| .NET XOR Packer | O | O | O | O |
| In-Memory .NET Loader | O | O | O | O |

[→ 전체 탐지 결과 및 모듈 설명 보기](https://github.com/VOID-wh4/bypass#전체-탐지-결과-요약)

---

### 🔬 [payload](https://github.com/VOID-wh4/payload)

페이로드 인코딩·난독화 PoC 모음.  
바이너리를 IPv4/IPv6/MAC 주소 문자열로 변환하는 HellShell 도구를 포함합니다.

| 프로젝트 | 설명 |
|---|---|
| [HellShell](https://github.com/VOID-wh4/payload/tree/main/HellShell) | 바이너리 → IPv4/IPv6/MAC 인코딩 + 독립 복원 C 코드 자동 생성 |

[→ 레포 보기](https://github.com/VOID-wh4/payload)

---

## 연구 대상

| 대상 | 버전 |
|---|---|
| Quasar RAT | v1.4.1 |
| Mimikatz | 최신 |

## 테스트 백신

nProtect · ALYac · V3 · Bitdefender · Avast · Kaspersky · McAfee · Windows Defender

---

## 팀원

| GitHub | 담당 |
|---|---|
| [@tortoiese](https://github.com/tortoiese) | APC Injection |
| [@hackers458](https://github.com/hackers458) | Manual PE Mapper, PebinForge, Hollowing Injection, Section Loader, PE-DLL Loader |
| [@VeryBigsilver](https://github.com/VeryBigsilver) | MBAPacker, AMSI Hooking, IPv4Fuscation |
| [@endusdksla](https://github.com/endusdksla) | ShellcodeLoader, Ghost Process Injection |
| [@zickzick2](https://github.com/zickzick2) | In-Memory .NET Assembly Loader |
| [@laneeeey](https://github.com/laneeeey) | dotnetXorPacker |
| [@Neo6424](https://github.com/Neo6424) | Process Injection |
| [@tjzln](https://github.com/tjzln) | |

---

<div align="center">
<sub>WhiteHat School 4기 사이드 프로젝트 · 교육 목적 보안 연구</sub>
</div>
