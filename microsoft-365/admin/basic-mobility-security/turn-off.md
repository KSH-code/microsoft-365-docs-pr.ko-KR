---
title: 기본 이동성 및 보안 해제
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 기본 이동성 및 보안을 해제 하기 위해 그룹 또는 정책을 제거 합니다.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430246"
---
# <a name="turn-off-basic-mobility-and-security"></a>기본 이동성 및 보안 해제

기본 이동성 및 보안을 효과적으로 해제 하려면 장치 관리 정책에서 보안 그룹으로 정의 된 사용자 그룹을 제거 하거나 정책 자체를 제거 합니다.

- 만든 장치 정책에서 사용자 보안 그룹을 제거 하 여 사용자 그룹을 제거 합니다.
    
- 모든 기본 이동성 및 보안 장치 정책을 제거 하 여 모든 사용자에 대해 기본 이동성 및 보안을 사용 하지 않도록 설정 합니다.
    
이러한 옵션은 조직의 장치에 대 한 기본 모바일 및 보안 적용을 제거 합니다. 아쉽게도 기본 이동성 및 보안을 설정한 후에는이를 "구축 취소" 할 수 없습니다. 

>[!IMPORTANT]
>정책에서 사용자 보안 그룹을 제거 하거나 정책 자체를 제거할 때 사용자의 장치에 미치는 영향에 대해 잘 알고 있어야 합니다. 예를 들어 장치에 따라 전자 메일 프로필 및 캐시 된 전자 메일이 제거 될 수 있습니다. 자세한 내용은  [정책을 삭제 하거나 정책에서 사용자를 제거 하는 경우 수행 되는 작업](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact) 을 참조 하세요.

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>기본 이동성 및 보안 장치 정책에서 사용자 보안 그룹 제거

1. 브라우저에서 다음을 입력  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 합니다.

2. 장치 정책을 선택 하 고 **정책 편집**을 선택 합니다. 

3.  **배포**   페이지에서 **제거**를 선택 합니다.
    
4.   **그룹**에서 보안 그룹을 선택 합니다.

5.  **제거**를 선택 하 고 **저장**을 선택 합니다.
    

## <a name="remove-basic-mobility-and-security-device-policies"></a>기본 모바일 및 보안 장치 정책 제거

1.  브라우저에서 다음을 입력  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 합니다. 

2.  장치 정책을 선택 하 고  **정책 삭제**를 선택 합니다.
    
3.  경고 대화 상자에서 **예**를 선택 합니다.

>[!NOTE] 
>조직 장치가 여전히 차단 상태인 경우 장치 차단을 해제 하는 방법에 대 한 자세한 내용은 [Office 365의 모바일 장치 관리에서 블로그 게시물 제거 액세스 제어](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)를 참조 하세요.
