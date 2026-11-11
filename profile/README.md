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

> 🔒 **실제 PoC 소스코드는 보안상 비공개 레포에 저장되어 있습니다.**  
> 아래 레포 링크는 접근 권한이 없는 경우 404가 표시될 수 있습니다.  
> 코드 열람이 필요하신 경우 팀원에게 별도로 문의해 주세요.

---

### 🛡️ bypass

AV/EDR 탐지 우회 기법 구현 모음.  
프로세스 인젝션, 후킹 우회, PE 로딩, 패킹 등 14개 모듈을 포함합니다.

| 카테고리 | 모듈 |
|---|---|
| 프로세스 인젝션 | APC Injection, Process Hollowing, Ghost Injection, Section Loader, Process Injection |
| 후킹 우회 | ntdll 언훅킹, AMSI Hooking (Detours / Frida) |
| PE 로딩 | Manual PE Mapper, In-Memory .NET Loader, PE-DLL Loader |
| 패킹 / 난독화 | MBAPacker, dotnetXorPacker, IPv4Fuscation |

**탐지 결과 — Quasar RAT v1.4.1**

`O` 우회 성공 · `X` 탐지 · `▲` 일부 기능 수행 시 탐지

> 🔒 백신 제품명은 비공개 레포에서만 확인할 수 있습니다. 열람이 필요한 경우 팀원에게 문의하세요.

| 기법 | AV-1 | AV-2 | AV-3 | AV-4 | AV-5 | AV-6 | AV-7 | AV-8 |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| APC Injection | O | O | O | X | O | X | X | X |
| Manual PE Mapper | O | O | O | X | O | O | O | O |
| Shellcode Loader | O | O | O | O | O | X | O | O |
| In-Memory .NET Assembly Loader | O | O | O | O | O | O | X | O |
| MBAPacker | O | O | X | O | X | X | X | O |
| Process Injection | O | O | O | X | X | X | O | X |
| .NET XOR Packer | O | O | O | O | O | O | X | O |

**탐지 결과 — Mimikatz**

| 기법 | AV-1 | AV-2 | AV-3 | AV-4 | AV-5 | AV-6 | AV-7 | AV-8 |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Process Hollowing | O | O | O | X | O | X | O | O |
| Manual PE Mapper | O | O | O | O | O | ▲ | O | O |
| Section Loader | O | O | O | X | O | X | O | O |
| Shellcode Loader | O | O | O | O | O | ▲ | O | O |
| MBAPacker | O | O | O | O | O | ▲ | O | O |
| PE-DLL Mapping | O | O | O | O | O | ▲ | O | O |
| Ghost Process Injection | O | O | O | X | O | X | O | O |
| ntdll Hooking | O | O | O | O | O | O | O | O |

---

### 🔬 payload

페이로드 인코딩·난독화 PoC 모음.  
바이너리를 IPv4/IPv6/MAC 주소 문자열로 변환하는 HellShell 도구를 포함합니다.

| 프로젝트 | 설명 |
|---|---|
| HellShell | 바이너리 → IPv4/IPv6/MAC 인코딩 + 독립 복원 C 코드 자동 생성 |

---

## 연구 대상

| 대상 | 버전 |
|---|---|
| Quasar RAT | v1.4.1 |
| Mimikatz | 최신 |

## 테스트 백신

국내외 상용 백신 8종 · 실제 제품명은 비공개 레포에서만 확인할 수 있습니다

---

## 팀원

<div align="center">
<table>
  <tr>
    <td align="center">
      <a href="https://github.com/tortoiese">
        <img src="https://github.com/tortoiese.png" width="70" alt="tortoiese"/><br/>
        <b>tortoiese</b>
      </a><br/>
      <sub>APC Injection</sub>
    </td>
    <td align="center">
      <a href="https://github.com/hackers458">
        <img src="https://github.com/hackers458.png" width="70" alt="hackers458"/><br/>
        <b>hackers458</b>
      </a><br/>
      <sub>Manual PE Mapper · PebinForge<br/>Hollowing · Section · PE-DLL Loader</sub>
    </td>
    <td align="center">
      <a href="https://github.com/VeryBigsilver">
        <img src="https://github.com/VeryBigsilver.png" width="70" alt="VeryBigsilver"/><br/>
        <b>VeryBigsilver</b>
      </a><br/>
      <sub>MBAPacker · AMSI Hooking<br/>IPv4Fuscation</sub>
    </td>
    <td align="center">
      <a href="https://github.com/endusdksla">
        <img src="https://github.com/endusdksla.png" width="70" alt="endusdksla"/><br/>
        <b>endusdksla</b>
      </a><br/>
      <sub>ShellcodeLoader<br/>Ghost Process Injection</sub>
    </td>
  </tr>
  <tr>
    <td align="center">
      <a href="https://github.com/zickzick2">
        <img src="https://github.com/zickzick2.png" width="70" alt="zickzick2"/><br/>
        <b>zickzick2</b>
      </a><br/>
      <sub>In-Memory .NET Assembly Loader</sub>
    </td>
    <td align="center">
      <a href="https://github.com/laneeeey">
        <img src="https://github.com/laneeeey.png" width="70" alt="laneeeey"/><br/>
        <b>laneeeey</b>
      </a><br/>
      <sub>dotnetXorPacker</sub>
    </td>
    <td align="center">
      <a href="https://github.com/Neo6424">
        <img src="https://github.com/Neo6424.png" width="70" alt="Neo6424"/><br/>
        <b>Neo6424</b>
      </a><br/>
      <sub>Process Injection</sub>
    </td>
    <td align="center">
      <a href="https://github.com/tjzln">
        <img src="https://github.com/tjzln.png" width="70" alt="tjzln"/><br/>
        <b>tjzln</b>
      </a>
    </td>
  </tr>
</table>
</div>

---

<div align="center">
<sub>WhiteHat School 4기 사이드 프로젝트 · 교육 목적 보안 연구</sub>
</div>
