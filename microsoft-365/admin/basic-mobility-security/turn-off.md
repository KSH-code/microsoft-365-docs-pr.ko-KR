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
ms.custom: AdminSurgePortfolio
description: 그룹 또는 정책을 제거하여 기본 이동성 및 보안을 해제합니다.
ms.openlocfilehash: 730c927c01bb7103c61694749ec7d55ec381a39a
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59775087"
---
# <a name="turn-off-basic-mobility-and-security"></a>기본 이동성 및 보안 해제

기본 이동성 및 보안을 효과적으로 해제하려면 장치 관리 정책에서 보안 그룹으로 정의된 사용자 그룹을 제거하거나 정책 자체를 제거합니다.

- 만든 장치 정책에서 사용자 보안 그룹을 제거하여 사용자 그룹을 제거합니다.

- 모든 기본 이동성 및 보안 장치 정책을 제거하여 모든 사용자에 대해 기본 이동성 및 보안을 사용하지 않도록 설정

이러한 옵션은 조직의 장치에 대한 기본 이동성 및 보안 적용을 제거합니다. 아쉽게도 기본 이동성 및 보안을 설정한 후에 단순히 "비프로비전"할 수 없습니다.

> [!IMPORTANT]
> 정책에서 사용자 보안 그룹을 제거하거나 정책 자체를 제거할 때 사용자의 장치에 미치는 영향을 알고 있어야 합니다. 예를 들어 장치에 따라 전자 메일 프로필 및 캐시된 전자 메일이 제거될 수 있습니다. 자세한 내용은 정책을 삭제하거나 정책에서 사용자를 제거하면 어떻게  [하나요?를 참조하세요.](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>기본 모바일 및 보안 장치 정책에서 사용자 보안 그룹 제거

1. 브라우저 유형:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. 장치 정책을 선택하고 정책 **편집 을 선택합니다.**

3. 배포  **페이지에서**   제거를 **선택합니다.**

4.   **그룹에서** 보안 그룹을 선택합니다.

5. 제거  **를** 선택하고 **저장을 선택합니다.**

## <a name="remove-basic-mobility-and-security-device-policies"></a>기본 모바일 및 보안 장치 정책 제거

1. 브라우저 유형:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. 장치 정책을 선택한 다음 정책  **삭제 를 선택합니다.**

3. 경고 대화 상자에서 예를 **선택합니다.**

> [!NOTE]
> 조직 장치가 여전히 차단된 상태인 경우 디바이스 차단을 해제하는 자세한 단계는 다음에서 액세스 제어 제거 블로그 [게시물을 Office 365용 모바일 장치 관리.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)
