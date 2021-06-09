---
title: BitLocker 암호화에 대한 관리
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 컴퓨터 및 Office 365 도난 BitLocker 데이터 도난 가능성을 줄이면서 암호화 암호화를 사용하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033626"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>암호화에 대한 BitLocker 및 분산 키 관리자(DKM)

Microsoft 서버는 BitLocker 볼륨 수준에서 고객 데이터가 포함된 디스크 드라이브를 암호화합니다. BitLocker 암호화는 기본 제공되는 데이터 보호 Windows. BitLocker 다른 프로세스 또는 제어(예: 하드웨어의 액세스 제어 또는 재생)에서 누군가가 고객 데이터를 포함하는 디스크에 물리적으로 액세스할 수 있는 경우 위협을 차단하는 데 사용되는 기술 중 하나입니다. 이 경우 BitLocker 컴퓨터 및 디스크를 분실, 도난 또는 부적절하게 해제하여 데이터 도난 또는 노출 가능성을 제거합니다.

BitLocker AES(Advanced Encryption Standard) 256비트 암호화를 사용하여 Exchange Online, SharePoint Online 및 비즈니스용 Skype. 디스크 섹터는 VMK(볼륨 마스터 키)로 암호화되는 FVEK(전체 볼륨 암호화 키)로 암호화되며, 이 키는 서버의 TPM(신뢰할 수 있는 플랫폼 모듈)에 바인딩됩니다. VMK는 FVEK를 직접 보호하므로 VMK를 보호하는 것이 중요합니다. 다음 그림에서는 주어진 서버에 대한 BitLocker 키 보호 체인의 예를 보여 주며 이 경우 Exchange Online 있습니다.

다음 표에서는 BitLocker 서버의 주요 보호 체인(이 경우 서버)에 대한 Exchange Online 설명을 제공합니다.

| 키 보호기 | 세분성 | 생성 방법 | 저장되는 위치 | 보호 |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256비트 외부 키 | 서버당 | BitLocker API | TPM 또는 비밀 안전 | Lockbox /Access Control |
|  |  |  | 사서함 서버 레지스트리 | TPM 암호화 |
| 48자리 숫자 암호 | 디스크당 | BitLocker API | Active Directory | Lockbox /Access Control |
| 공개 키 보호기라고도 하는 X.509 DRA(데이터 복구 에이전트)로 인증서 | 환경(예: Exchange Online) | Microsoft CA | 빌드 시스템 | 개인 키에 대한 전체 암호가 있는 사용자는 없습니다. 암호가 물리적으로 보호됩니다. |


BitLocker 키 관리에는 Microsoft 데이터 센터에서 암호화된 디스크의 잠금을 해제/복구하는 데 사용되는 복구 키 관리가 필요합니다. Microsoft 365 보안 공유에 마스터 키를 저장하며, 선별 및 승인된 개인만 액세스할 수 있습니다. 키의 자격 증명은 액세스 제어 데이터("비밀 저장소"라고도 하는)를 위한 보안 리포지토리에 저장됩니다. 이 저장소를 사용하려면 제시간 액세스 권한 상승 도구를 사용하여 액세스하려면 높은 수준의 권한 상승 및 관리 승인이 필요합니다.

BitLocker 두 관리 범주에 속하는 키를 지원할 수 있습니다.

- BitLocker 관리되는 키로, 일반적으로 수명이 짧은 키로, 서버에 설치된 운영 체제 인스턴스의 수명 또는 해당 디스크에 연결됩니다. 이러한 키는 서버 다시 설치 또는 디스크 서식을 설정하는 동안 삭제되고 다시 설정됩니다.

- BitLocker 외부에서 관리되지만 디스크 암호 해독에 BitLocker 복구 키가 필요합니다. BitLocker 운영 체제가 다시 설치되고 암호화된 데이터 디스크가 이미 있는 시나리오에 복구 키를 사용하게 됩니다. 복구 키는 응답자는 디스크의 잠금을 해제해야 하는 Exchange Online 관리되는 가용성 모니터링 프로브에서도 사용됩니다.

BitLocker 보호된 볼륨은 볼륨 마스터 키로 암호화되는 전체 볼륨 암호화 키로 암호화됩니다. BitLocker 암호화 키가 유선으로 저장되거나 유선으로 전송되지 않도록 FIPS 호환 알고리즘을 사용합니다. 고객 Microsoft 365 저장 보호를 구현하는 것은 기본 데이터 보호 구현과 BitLocker 않습니다.
