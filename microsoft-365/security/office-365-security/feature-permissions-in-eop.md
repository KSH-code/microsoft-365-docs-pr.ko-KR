---
title: EOP의 기능 사용 권한
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Microsoft EOP(Exchange Online Protection)를 관리하기 위한 작업을 수행하는 데 필요한 사용 권한은 관리 대상 기능에 따라 다릅니다.
ms.openlocfilehash: 2129df7faaa977d59f8af8082291520d33bc9cc7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599315"
---
# <a name="feature-permissions-in-eop"></a>EOP의 기능 사용 권한

EOP (Exchange Online Protection)를 관리 하기 위한 작업을 수행 하는 데 필요한 사용 권한은 관리 대상 기능에 따라 다릅니다.

EOP를 설정하려면 Office 365 전역 관리자 또는 Exchange 회사 관리자(조직 관리 역할 그룹)여야 합니다.

## <a name="exchange-online-protection-permissions"></a>Exchange Online Protection 사용 권한

EOP 기능을 관리하는 데 필요한 사용 권한을 확인하려면 다음 표를 참조하세요. 하나의 기능에 둘 이상의 역할 그룹이 나열되는 경우 기능을 사용할 역할 그룹 중 하나만 할당되어야 합니다.

|**기능**|**필요한 권한**|
|:-----|:-----|
|맬웨어 방지|조직 관리 <br/><br/> 예방 조치 관리|
|스팸 방지|조직 관리 <br/><br/> 예방 조치 관리|
|메일 흐름 규칙|조직 관리 <br/><br/> 레코드 관리|
|도메인|조직 관리 <br/><br/> 보기 전용 조직 관리|
|ATP (Advanced Threat Protection)|조직 관리 <br/><br/> 예방 조치 관리|
|Office 365 커넥터|조직 관리|
|Message trace|조직 관리 <br/><br/> 보기 전용 조직 관리|
|조직 구성|조직 관리|
|격리|조직 관리 <br/><br/> 보기 전용 조직 관리 <br/><br/> 예방 조치 관리|
|사용자, 연락처 및 역할 그룹|조직 관리 <br/><br/> 보기 전용 조직 관리 <br/><br/> 예방 조치 관리|
|메일 그룹 및 보안 그룹|조직 관리 <br/><br/> 보기 전용 조직 관리 <br/><br/> 예방 조치 관리|
|보고서 보기|조직 관리: 메일 보호 보고서에 액세스할 수 있습니다. <br/><br/> 보기 전용 받는 사람: 메일 보호 보고서에 액세스할 수 있습니다.  <br/><br/> 준수 관리: 메일 보호 보고서 및 DLP (데이터 손실 방지) 보고서에 액세스 합니다 (구독에 DLP 기능이 있는 경우).|
