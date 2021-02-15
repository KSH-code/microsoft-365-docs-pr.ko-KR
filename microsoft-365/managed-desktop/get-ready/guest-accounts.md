---
title: 게스트 계정에 대한 필수 구성 요소
description: 게스트 계정에 대한 구성 지침 및 조정 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073227"
---
# <a name="prerequisites-for-guest-accounts"></a>게스트 계정에 대한 필수 구성 요소

Microsoft Managed Desktop을 사용하려면 Azure AD 조직에서 게스트 계정 액세스를 위해 다음 설정이 필요합니다. 외부 ID/외부 공동 작업에서 [Azure Portal에서](https://portal.azure.com) **이러한 설정을 조정할 수 있습니다.**

-   **게스트 초대자** 역할의 관리자 및 사용자는 예로 설정하여 초대할 수 **있습니다.**
-   공동 **작업 제한의 경우** 다음 옵션을 선택합니다.
    -   모든 **도메인(가장** 포함)으로 초대를 보낼 수 있도록 선택하면 다른 구성이 필요하지 않습니다.
    -   지정된 도메인에 대한 초대 거부를 선택하는 경우 대상 도메인에 Microsoft.com 목록에 없는지 확인 합니다. 
    -   지정된 도메인(가장 제한적인)에 대한 초대만 허용을 선택하는 경우  Microsoft.com 도메인에 나열되어 있는지 확인해야 합니다. 

이러한 설정과 상호 작용하는 제한을 설정하는 경우 Azure Active Directory 최신 작업 공간 서비스 계정을 **제외해야 합니다.** 예를 들어 게스트 계정이 Intune 포털에 액세스하지 못하게 하는 조건부 액세스 정책이 있는 경우 이 정책에서 최신 **Workplace Service Accounts** 그룹을 제외합니다.

