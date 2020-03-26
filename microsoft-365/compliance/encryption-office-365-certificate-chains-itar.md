---
title: Office 365 암호화 체인-DOD 및 GCC High
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/24/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Office 365에서 DOD 및 GCC 상위 루트 인증서 및 CAs (인증 기관)의 전체 목록을 확인 합니다.
ms.openlocfilehash: 615a62b2ae2a954580ebf82f4c1b70748c991a71
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951906"
---
# <a name="office-365-encryption-chains---dod-and-gcc-high"></a>Office 365 암호화 체인-DOD 및 GCC High

Office 365에서는 다양 한 인증서 공급자를 활용 합니다. 다음은 Office 365에 액세스할 때 **, DOD 및 GCC 최고 고객에 게** 발생할 수 있는 알려진 Office 365 루트 인증서의 전체 목록을 설명 합니다. 자체 인프라에서 설치 해야 할 수 있는 인증서에 대 한 자세한 내용은 [Office 365 용 타사 SSL 인증서 계획](https://docs.microsoft.com/office365/enterprise/plan-for-third-party-ssl-certificates)을 참조 하십시오.

다음 인증서 정보는 **모든 DOD 및 GCC 최고 고객**에 게 적용 됩니다.

>[!NOTE]
>**전 세계 고객**에 게 적용 되는 인증서 정보는 [Office 365 암호화 체인](encryption-office-365-certificate-chains.md)을 참조 하십시오.

| **인증서 형식** | **P7b 다운로드** | **CRL 끝점** | **OCSP 끝점** |
| --- | --- | --- | --- | --- |
| 공개적으로 신뢰할 수 있는 루트 및 중간 인증서 | [Office 365 ITAR 인증서 번들 (P7B)](https://download.microsoft.com/download/b/3/a/b3ae08a2-516c-46a9-8723-6256e4fd6383/O365_Chain_Certs_ITAR20200304.p7b) | crl.entrust.net<br>crl3.digicert.com<br>crl4.digicert.com | ocsp.digicert.com<br>ocsp.entrust.net |

아래 루트 및 중간 섹션을 확장 하 여 인증서 공급자에 대 한 추가 정보를 확인 합니다.

## <a name="office-365-certificate-details"></a>**Office 365 인증서 세부 정보**

### <a name="baltimore-cybertrust-root"></a>**Baltimore CyberTrust Root**

| **제목** | CN = Baltimore CyberTrust Root<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| --- | --- |
| **일련 번호** | 02:00:00: B9 |
| **공개 키 길이** | RSA 2048 비트 (e 65537) |
| **서명 알고리즘** | sha1RSA |
| **유효 하지 않음** | UTC 년 5 월 12 18:46:00 2000 |
| **유효 하지 않음** | UTC 년 5 월 12 23:59:00 2025 |
| **주체 키 식별자** | e5:9d: 59:30:82:47:58: cc: ac: fa: 08:54:36:86:7b: 3a: f0 |
| **지문 (SHA-1)** | D4DE20D05E66FC53FE1A50882C78DB2852CAE474 |
| **지문 (SHA-256)** | 16AF57A9F676B0AB126095AA5EBADEF22AB31119D644AC95CD4B93DBF3F26AEB |
| **Pin (SHA-256)** | Y9mvm0exBk1JoQ57f9Vm28jKo5lFm/woKcVxrYxu80o = |

### <a name="digicert-cloud-services-ca-1"></a>**DigiCert Cloud Services CA-1**

| **제목** | CN = DigiCert Cloud Services CA-1<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **발급** | CN = DigiCert 전역 루트 CA<br>OU = digicert<br>O = DigiCert Inc<br>C = US |
| **일련 번호** | 01:9E: C1: C6: BD: C A X: 59:7B: 0 |
| **공개 키 길이** | RSA 2048 비트 (e 65537) |
| **서명 알고리즘** | sha256RSA |
| **유효 하지 않음** | 8 월 04 12:00:00 2015 일 UTC |
| **유효 하지 않음** | 8 월 04 12:00:00 2030 일 UTC |
| **주체 키 식별자** | dd: 51: d0: a2:31:73: a9:73:8f: 7e: 5d: 8c: 9f: f0: f7 |
| **인증 기관 키 식별자** | keyid: 03: de: 50:35:10: d1:4c: b: 66: f0: a3 = e2:1b: 1:03:97-1b: 3d: d1 |
| **지문 (SHA-1)** | 81B68D6CD2F221F8F534E677523BB236BBA1DC56 |
| **지문 (SHA-256)** | 2F6889961A7CA7067E8BA103C2CF9B9A924F8CA293F11178E23A1978D2F133D3 |
| **Pin (SHA-256)** | UgpUVparimk8QCjtWQaUQ7EGrtrykc/L8N66EhFY3VE = |
| **CRL Url** | http://crl4.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl3.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP Url** | http://ocsp.digicert.com |

### <a name="digicert-global-root-ca"></a>**DigiCert 전역 루트 CA**

| **제목** | CN = DigiCert 전역 루트 CA<br>OU = digicert<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **일련 번호** | 08:3B: E0:56:90:42:46: B1: A1:75:6A: C 9:59:91: C7:4A |
| **공개 키 길이** | RSA 2048 비트 (e 65537) |
| **서명 알고리즘** | sha1RSA |
| **유효 하지 않음** | 11 월 10 00:00:00 2006 UTC |
| **유효 하지 않음** | 11 월 10 00:00:00 2031 UTC |
| **주체 키 식별자** | 03: de: 50:35:10: d1:4c: 1b: 2 x: f0: a3: c 3:3: a x 3. |
| **인증 기관 키 식별자** | keyid: 03: de: 50:35:10: d1:4c: b: 66: f0: a3 = e2:1b: 1:03:97-1b: 3d: d1 |
| **지문 (SHA-1)** | A8985D3A65E5E5C4B2D7D66D40C6DD2FB19C5436 |
| **지문 (SHA-256)** | 4348A0E9444C78CB265E058D5E8944B4D84F9662BD26DB257F8934A443C70161 |
| **Pin (SHA-256)** | r/mIkG3eEpVdm + u/ko-kr/cwxzOMo1bk4TyHIlByibiA5E = |

### <a name="digicert-high-assurance-ev-root-ca"></a>**DigiCert High 보증 EV 루트 CA**

| **제목** | CN = DigiCert High 보증 EV 루트 CA<br>OU = digicert<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **일련 번호** | 02: AC: 5C: 26:6A: 0B: 40:9B: 8F: 0B: 79: F2: AE: 46:25:77 |
| **공개 키 길이** | RSA 2048 비트 (e 65537) |
| **서명 알고리즘** | sha1RSA |
| **유효 하지 않음** | 11 월 10 00:00:00 2006 UTC |
| **유효 하지 않음** | 11 월 10 00:00:00 2031 UTC |
| **주체 키 식별자** | b1:3e: c3:69:03: f8: f m: 1:01:18의 경우. e m a = 1 = 08 |
| **인증 기관 키 식별자** | keyid: b1:3e: e 3:69:03: f8: bf: 47:1: f m a. 1. |
| **지문 (SHA-1)** | 5FB7EE0633E259DBAD0C4C9AE6D38F1A61C7DC25 |
| **지문 (SHA-256)** | 7431E5F4C3C1CE4690774F0B61E05440883BA9A01ED00BA6ABD7806ED3B118CF |
| **Pin (SHA-256)** | WoiWRyIOVNa9ihaBciRSC7XHjliYS9VwUGOIud4PB18 = |

### <a name="digicert-sha2-extended-validation-server-ca"></a>**DigiCert SHA2 확장 유효성 검사 서버 CA**

| **제목** | CN = DigiCert SHA2 Extended Validation Server CA<br>OU = digicert<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **일련 번호** | 0C: 79: A9:44: B0:8C: 11:95:20:92:5F: 6B: 1D: 83 |
| **공개 키 길이** | RSA 2048 비트 (e 65537) |
| **서명 알고리즘** | sha256RSA |
| **유효 하지 않음** | UTC 년 10 월 22 00:00:00 2013 일 |
| **유효 하지 않음** | UTC 년 10 월 22 00:00:00 2028 일 |
| **주체 키 식별자** | 3D: D3:50: A5: A0: '%: EE: F X F F F F: F F F F X: 4A: 60, 0A: 65: D3:21: D4: F8: F8: D6:0F |
| **인증 기관 키 식별자** | keyID: b1:3e: e 3:69:03: f8: bf: 47:1: f m a. 1. |
| **지문 (SHA-1)** | 7E2F3A4F8FE8FA8A5730AECA029696637E986F3F |
| **지문 (SHA-256)** | 403E062A2653059113285BAF80A0D4AE422C848C9F78FAD01FC94BC5B87FEF1A |

### <a name="entrust-root-certification-authority"></a>**Entrust 루트 인증 기관**

| **제목** | CN = Entrust 루트 인증 기관<br>OU = "(c) 2006 Entrust, Inc."<br>OU = entrust/CPS가 참조로 통합 됨<br>OU = www.entrust.net/legal-terms 참조<br>O =&quot;Entrust, i n c.&quot;<br>C = US |
| --- | --- |
| **일련 번호** | 45:6B: 50:54 |
| **공개 키 길이** | RSA 2048 비트 (e 65537) |
| **서명 알고리즘** | sha1RSA |
| **유효 하지 않음** | 11 월 27 12:23:42 2006 UTC |
| **유효 하지 않음** | 11 월 27 12:53:42 2026 UTC |
| **주체 키 식별자** | 68:90: E4:67: A4: A6:53:80: C7:86:66: A4: F1: F7:4B: 43: FB: 84: BD: 6D |
| **인증 기관 키 식별자** | keyID: 68:90: e4:67: a4: a6:53:80: c7:86:66: a4: f1: f7:4b: 43: fb: 84: bd: 6d |
| **지문 (SHA-1)** | B31EB1B740E36C8402DADC37D44DF5D4674952F9 |
| **지문 (SHA-256)** | 73C176434F1BC6D5ADF45B0E76E727287C8DE57616C1E6E6141A2B2CBC7D8E4C |

### <a name="entrust-root-certification-authority---g2"></a>**Entrust 루트 인증 기관-G2**

| **제목** | CN = Entrust 루트 인증 기관-G2<br>OU =&quot;(c) 2009 Entrust, Inc.-권한 있는 사용에만 해당&quot;<br>OU = www.entrust.net/legal-terms 참조<br>O =&quot;Entrust, i n c.&quot;<br>C = US |
| --- | --- |
| **일련 번호** | 4A: 53:8C: 28 |
| **공개 키 길이** | RSA 2048 비트 (e 65537) |
| **서명 알고리즘** | sha256RSA |
| **유효 하지 않음** | 7 월 07 17:25:54 2009 일 UTC |
| **유효 하지 않음** | 12 월 07 17:55:54 2030 일 UTC |
| **주체 키 식별자** | 6a: 72:26:7a: d0:1e: ef: 7d: e7:3b: 25:8d: 9f:!: 12:66: ab |
| **지문 (SHA-1)** | 8CF427FD790C3AD166068DE81E57EFBB932272D4 |
| **지문 (SHA-256)** | 43DF5774B03E7FEF5FE40D931A7BEDF1BB2E6B42738C4E6D3841103D3AA7F339 |
| **Pin (SHA-256)** | du6FkDdMcVQ3u8prumAo6t3i3G27uMP2EOhR8R0at/U = |

### <a name="entrustnet-certification-authority-2048"></a>**Entrust.net Certification Authority (2048)**

| **제목** | CN = Entrust 인증 기관 (2048)<br>OU = (c) 1999 Entrust.net 제한 됨<br>OU = entrust/CPS\_2048 incorp ref. (s liab 제한)<br>O = Entrust |
| --- | --- |
| **일련 번호** | 38:63: DE: F8 |
| **공개 키 길이** | RSA 2048 비트 (e 65537) |
| **서명 알고리즘** | sha1RSA |
| **유효 하지 않음** | 12 월 24 17:50:51 1999 일 UTC |
| **유효 하지 않음** | 7 월 24 14:15:12 2029 일 UTC |
| **주체 키 식별자** | 55: e4:81;: d1:11:80:1: d8:11: b9: e x: a x 8. |
| **지문 (SHA-1)** | 503006091D97D4F5AE39F7CBE7927D7D652D3431 |
| **지문 (SHA-256)** | 6DC47172E01CBCB0BF62580D895FE2B8AC9AD4F873801E0C10B9C837D21EB177 |
| **Pin (SHA-256)** | HqPF5D7WbC2imDpCpKebHpBnhs6fG1hiFBmgBGOofTg = |

### <a name="entrust-certification-authority---l1c"></a>**Entrust 인증 기관-L1C**

| **제목** | CN = Entrust 인증 기관-L1C<br>OU =&quot;(c) 2009 Entrust, inc.&quot;<br>OU = entrust/rpa가 참조로 통합 됨<br>O =&quot;Entrust, i n c.&quot;<br>C = US |
| --- | --- |
| **발급** | CN = Entrust 인증 기관 (2048)<br>OU = (c) 1999 Entrust.net 제한 됨<br>OU = entrust/CPS\_2048 incorp ref. (제한 liab)<br>O = Entrust |
| **일련 번호** | 4C: 0E: 8C: 39 |
| **공개 키 길이** | RSA 2048 비트 (e 65537) |
| **서명 알고리즘** | sha1RSA |
| **유효 하지 않음** | 11 월 11 15:40:40 2011 UTC |
| **유효 하지 않음** | 11 월 11 02:51:17 2021 UTC |
| **주체 키 식별자** | 1e: f1: ab: 89:06: f8:49:0f: 01:33:77: ee: 14:7a: ee: 19 = 7c: 1:4d |
| **인증 기관 키 식별자** | keyid: 55: e4: e 1: d1:10: ' r e r e r a x:: 11 = 80-08:8 |
| **지문 (SHA-1)** | C53E73073F93CE7895DE7484126BC303DAB9E657 |
| **지문 (SHA-256)** | 0EE4DAF71A85D842D23F4910FD4C909B7271861931F1D5FEAC868225F52700E2 |
| **Pin (SHA-256)** | VFv5NemtodoRftw8KsvFb8AoCWwOJL6bOJS + Ui0bQ94 = |
| **CRL Url** | http://crl.entrust.net/2048ca.crl |
| **OCSP Url** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1e"></a>**Entrust 인증 기관-L1E**

| **제목** | CN = Entrust 인증 기관-L1E<br>OU =&quot;(c) 2009 Entrust, inc.&quot;<br>OU = entrust/rpa가 참조로 통합 됨<br>O =&quot;Entrust, i n c.&quot;<br>C = US |
| --- | --- |
| **발급** | CN = Entrust 인증 기관 (2048)<br>OU = (c) 1999 Entrust.net 제한 됨<br>OU = entrust/CPS\_2048 incorp ref. (제한 liab)<br>O = Entrust |
| **일련 번호** | 4C: 0E: C 9:18 |
| **공개 키 길이** | RSA 2048 비트 (e 65537) |
| **서명 알고리즘** | sha1RSA |
| **유효 하지 않음** | 11 월 11 15:40:40 2011 UTC |
| **유효 하지 않음** | 11 월 11 02:51:17 2021 UTC |
| **주체 키 식별자** | 5B: 41:8A, B2: C4:1: 2. C A P 3.2.2. C A P F P C 1. X X: C8:: F A 3: 다음을 수행 합니다. |
| **인증 기관 키 식별자** | keyid: 68:90: e4:67: a4: a6:53:80: c7:86:66: a4: f1: f7:4b: 43: fb: 84: bd: 6d |
| **지문 (SHA-1)** | 8A000CC056F7D17349F045BEB0319A3B91C9F979 |
| **지문 (SHA-256)** | 3C7A634E5778A0F731972B702DAE24B2CF2060219F607E69878B164C61A06C41 |
| **CRL Url** | http://crl.entrust.net/rootca1.crl |
| **OCSP Url** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1k"></a>**Entrust 인증 기관-L1K**

| **제목** | CN = Entrust 인증 기관-L1K<br>OU =&quot;(c) 2012 Entrust, Inc.-권한 있는 사용에만 해당&quot;<br>OU = www.entrust.net/legal-terms 참조<br>O =&quot;Entrust, i n c.&quot;<br>C = US |
| --- | --- |
| **발급** | CN = Entrust 루트 인증 기관-G2<br>OU =&quot;(c) 2009 Entrust, Inc.-권한 있는 사용에만 해당&quot;<br>OU = www.entrust.net/legal-terms 참조<br>O =&quot;Entrust, i n c.&quot;<br>C = US |
| **일련 번호** | 0E: E9:4C: 03:00:00:00:00:51: D3:77:85 |
| **공개 키 길이** | RSA 2048 비트 (e 65537) |
| **서명 알고리즘** | sha256RSA |
| **유효 하지 않음** | UTC 년 10 월 05 19:13:56 2015 일 |
| **유효 하지 않음** | 12 월 05 19:43:56 2030 일 UTC |
| **주체 키 식별자** | 82: a2:70:74:82: bc: 53:에 안 됩니다. cf: 7b: d4: ' c a x: f x: f x; |
| **인증 기관 키 식별자** | keyid: 6a: 72:26:7a: d0:1e: ef: 7d: e7:3b: 69:8d: 9f: |
| **지문 (SHA-1)** | F21C12F46CDB6B2E16F09F9419CDFF328437B2D7 |
| **지문 (SHA-256)** | 13EFB39A2F6654E8C67BD04F4C6D4C90CD6CAB5091BCEDC73787F6B77D3D3FE7 |
| **Pin (SHA-256)** | 980Ionqp3wkYtN9SZVgMzuWQzJta1nfxNPwTem1X0uc = |
| **CRL Url** | http://crl.entrust.net/g2ca.crl |
| **OCSP Url** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1m"></a>**Entrust 인증 기관-L1M**

| **제목** | CN = Entrust 인증 기관-L1M, OU =&quot;(c) 2014 Entrust, Inc.-권한 있는 사용에만 해당&quot;<br>OU = www.entrust.net/legal-terms 참조<br>O =&quot;Entrust, i n c.&quot;<br>C = US |
| --- | --- |
| **발급** | CN = Entrust 루트 인증 기관-G2<br>OU =&quot;(c) 2009 Entrust, Inc.-권한 있는 사용에만 해당&quot;<br>OU = www.entrust.net/legal-terms 참조<br>O =&quot;Entrust, i n c.&quot;<br>C = US |
| **일련 번호** | 61: A1: E7: D2:00:00:00:00:51: D3:66: A6 |
| **공개 키 길이** | RSA 2048 비트 (e 65537) |
| **서명 알고리즘** | sha256RSA |
| **유효 하지 않음** | 12 월 15 07:25:03 2014 일 UTC |
| **유효 하지 않음** | UTC 년 10 월 15 08:55:03 2030 일 |
| **주체 키 식별자** | C3: F7: D0: B5:2A: 30: AD: AF: 0D: 91:21:70:39:54:7: BC: 89:70: C7:3A |
| **인증 기관 키 식별자** | keyid: 6a: 72:26:7a: d0:1e: ef: 7d: e7:3b: 69:8d: 9f: |
| **지문 (SHA-1)** | CC136695639065FAB47074D28C55314C66077E90 |
| **지문 (SHA-256)** | 75C5B3F01FD1F51A2C447AB7C785D72E69FA9C472C08571E7EADF3B8EABAE70C |
| **CRL Url** | http://crl.entrust.net/g2ca.crl |
| **OCSP Url** | http://ocsp.entrust.net |

### <a name="microsoft-it-tls-ca-1"></a>**Microsoft IT TLS CA 1**

| **제목** | CN = Microsoft IT TLS CA 1<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = 인천<br>C = US |
| --- | --- |
| **발급** | CN = Baltimore CyberTrust Root<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| **일련 번호** | 08: B8:7A: 50:1B: BE: 9C: DA: 2D: 16:4D: 3E: 39:51: BF: 55 |
| **공개 키 길이** | RSA 4096 비트 (e 65537) |
| **서명 알고리즘** | sha256RSA |
| **유효 하지 않음** | UTC 년 5 월 20 12:51:28 2016 |
| **유효 하지 않음** | UTC 년 5 월 20 12:51:28 2024 |
| **주체 키 식별자** | 58:88:9f: d6: dc: 9c: 48:22: b7:14:3e: ff: 84:88: e8: e6:85: ff: fa: 7d |
| **인증 기관 키 식별자** | keyid: e5:9d: 59:30:82:47:58: cc: ac: fa: 08:54:36:86:7b: 3a: b5: f0 |
| **지문 (SHA-1)** | 417E225037FBFAA4F95761D5AE729E1AEA7E3A42 |
| **지문 (SHA-256)** | 4FF404F02E2CD00188F15D1C00F4B6D1E38B5A395CF85314EAEBA855B6A64B75 |
| **Pin (SHA-256)** | xjXxgkOYlag7jCtR5DreZm9b61iaIhd + J3 + b2LiybIw = |
| **CRL Url** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP Url** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-2"></a>**Microsoft IT TLS CA 2**

| **제목** | CN = Microsoft IT TLS CA 2<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = 인천<br>C = US |
| --- | --- |
| **발급** | CN = Baltimore CyberTrust Root<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| **일련 번호** | 0F: 2C: 10: C 9:5B: 06: C0:93:7F: B8: D4 = 49: F8:3E: 85: |
| **공개 키 길이** | RSA 4096 비트 (e 65537) |
| **서명 알고리즘** | sha256RSA |
| **유효 하지 않음** | UTC 년 5 월 20 12:51:57 2016 |
| **유효 하지 않음** | UTC 년 5 월 20 12:51:57 2024 |
| **주체 키 식별자** | 91:9e: 3b: 44:6c: 3d: 57:9c: 42:77:4f: d1: cc: 4a: 97 = 2c: da |
| **인증 기관 키 식별자** | keyid: e5:9d: 59:30:82:47:58: cc: ac: fa: 08:54:36:86:7b: 3a: b5: f0 |
| **지문 (SHA-1)** | 54D9D20239080C32316ED9FF980A48988F4ADF2D |
| **지문 (SHA-256)** | 4E107C981B42ACBE41C01067E16D44DB64814D4193E572317EA04B87C79C475F |
| **Pin (SHA-256)** | wBdPad95AU7OgLRs0FU/E6ILO1MSCM84kJ9y0H + TT7s = |
| **CRL Url** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP Url** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-4"></a>**Microsoft IT TLS CA 4**

| **제목** | CN = Microsoft IT TLS CA 4<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = 인천<br>C = US |
| --- | --- |
| **발급** | CN = Baltimore CyberTrust Root<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| **일련 번호** | 0B: 6A: B3: B0:3E: B1: A9: F6: ' C4: F X: F A R: A8: CD: FE: B3 |
| **공개 키 길이** | RSA 4096 비트 (e 65537) |
| **서명 알고리즘** | sha256RSA |
| **유효 하지 않음** | UTC 년 5 월 20 12:52:38 2016 |
| **유효 하지 않음** | UTC 년 5 월 20 12:52:38 2024 |
| **주체 키 식별자** | 7a: 7b: 8c: c1: cf: e7: a0:6b: fb:: 0f: 33: c3: |
| **인증 기관 키 식별자** | keyid: e5:9d: 59:30:82:47:58: cc: ac: fa: 08:54:36:86:7b: 3a: b5: f0 |
| **지문 (SHA-1)** | 8A38755D0996823FE8FA316EAC4E99 |
| **지문 (SHA-256)** | 5FFAC43E0DDC5B4AF2B696F6BC4DB7E91DF314BB8FE0D0713A0B1A7AD2A68FAC |
| **Pin (SHA-256)** | wUY9EOTJmS7Aj4fDVCu/KeE + + mV7FgIcbn4WhMz1I2k = |
| **CRL Url** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP Url** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-5"></a>**Microsoft IT TLS CA 5**

| **제목** | CN = Microsoft IT TLS CA 5<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = 인천<br>C = US |
| --- | --- |
| **발급** | CN = Baltimore CyberTrust Root<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| **일련 번호** | 08:88: CD: 52:5F: 19:24:44:4D: 14: A5:82:91: DE: B9:52 |
| **공개 키 길이** | RSA 4096 비트 (e 65537) |
| **서명 알고리즘** | sha256RSA |
| **유효 하지 않음** | UTC 년 5 월 20 12:53:03 2016 |
| **유효 하지 않음** | UTC 년 5 월 20 12:53:03 2024 |
| **주체 키 식별자** | 08: fe: 25:9f: 74: ea: 87:04: c2: bc: bb: 8e: a8:38을 5f: 33 |
| **인증 기관 키 식별자** | keyid: e5:9d: 59:30:82:47:58: cc: ac: fa: 08:54:36:86:7b: 3a: b5: f0 |
| **지문 (SHA-1)** | AD898AC73DF333EB60AC1F5FC6C4B2219DDB79B7 |
| **지문 (SHA-256)** | F0EE5914ED94C7252D058B4E39808AEE6FA8F62CF0974FB7D6D2A9DF16E3A87F |
| **Pin (SHA-256)** | RCbqB + W8nwjznTeP4O6VjqcwdxIgI79eBpnBKRr32gc = |
| **CRL Url** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP Url** | http://ocsp.digicert.com |
