---
title: 끝점용 Microsoft Defender에서 경고 알림 구성
description: 끝점용 Microsoft Defender를 사용하여 심각도 및 기타 기준에 따라 보안 경고에 대한 전자 메일 알림 설정을 구성할 수 있습니다.
keywords: 전자 메일 알림, 경고 알림 구성, 끝점용 Microsoft Defender, 끝점 알림용 Microsoft Defender, 끝점 경고용 Microsoft Defender, Windows 10 Enterprise, Windows 10 Education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 857df1a9f088c316349fbbe02618a7345df5a075
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222004"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에서 경고 알림 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-emailconfig-abovefoldlink)

새 경고에 대해 지정된 받는 사람에게 전자 메일 알림을 보내도록 끝점에 대한 Defender를 구성할 수 있습니다. 이 기능을 사용하면 즉시 알림을 보내고 심각도에 따라 경고에 대해 행동할 수 있는 개인 그룹을 식별할 수 있습니다.

> [!NOTE]
> '보안 설정 관리' 권한이 있는 사용자만 전자 메일 알림을 구성할 수 있습니다. 기본 사용 권한 관리를 사용하도록 선택한 경우 보안 관리자 또는 전역 관리자 역할이 있는 사용자는 전자 메일 알림을 구성할 수 있습니다.

알림을 트리거하는 경고 심각도 수준을 설정할 수 있습니다. 전자 메일 알림의 받는 사람을 추가하거나 제거할 수도 있습니다. 새 받는 사람은 추가된 후 트리거된 경고에 대한 알림을 받을 수 있습니다. 경고에 대한 자세한 내용은 경고 큐 보기 및 [구성을 참조하세요.](alerts-queue.md)

RBAC(역할 기반 액세스 제어)를 사용하는 경우 받는 사람은 알림 규칙에 구성된 장치 그룹을 기반으로 하는 알림만 받게 됩니다.
적절한 권한이 있는 사용자는 장치 그룹 관리 범위로 제한되는 알림만 만들거나 편집하거나 삭제할 수 있습니다.
전역 관리자 역할에 할당된 사용자만 모든 장치 그룹에 대해 구성된 알림 규칙을 관리할 수 있습니다.

전자 메일 알림에는 경고에 대한 기본 정보와 추가 조사를 할 수 있는 포털 링크가 포함됩니다.

## <a name="create-rules-for-alert-notifications"></a>경고 알림에 대한 규칙 만들기
장치 및 알림 심각도 및 알림 받는 사람에 대해 전자 메일 알림을 보내기 위한 규칙을 만들 수 있습니다.


1. 탐색 창에서 **끝점 일반 설정** 알림을 \>  \>  \> **선택합니다.**

2. 항목 **추가 를 클릭합니다.**

3. 일반 정보를 지정합니다.
    - **규칙 이름** - 알림 규칙의 이름을 지정합니다.
    - **조직 이름 포함** - 전자 메일 알림에 나타나는 고객 이름을 지정합니다.
    - **테넌트별** 포털 링크 포함 - 테넌트 ID가 포함된 링크를 추가하여 특정 테넌트에 대한 액세스를 허용합니다.
    - **장치 정보 포함** - 전자 메일 경고 본문에 장치 이름을 포함합니다.

        > [!NOTE]
        > 이 정보는 끝점 데이터용 Defender에 대해 선택한 지리적 위치에 없는 받는 사람 메일 서버에서 처리될 수 있습니다.

    - **장치** - 받는 사람에게 모든 장치(전역 관리자 역할에만 해당) 또는 선택한 장치 그룹의 경고를 받는 사람에게 알릴지 여부를 선택하십시오. 자세한 내용은 장치 그룹 [만들기 및 관리를 참조하세요.](machine-groups.md)
    - **경고 심각도** - 경고 심각도 수준을 선택 합니다.

4. **다음** 을 클릭합니다.

5. 받는 사람의 전자 메일 주소를 입력한 다음 받는 사람 **추가를 클릭합니다.** 이메일 주소를 여러 개 추가할 수 있습니다.

6. 테스트 전자 메일 보내기 를 선택하여 전자 메일 받는 사람이 전자 메일 알림을 **받을 수 있는지 확인**

7. 알림 **규칙 저장을 클릭합니다.**

## <a name="edit-a-notification-rule"></a>알림 규칙 편집

1. 편집할 알림 규칙을 선택합니다.

2. 일반 및 받는 사람 탭 정보를 업데이트합니다.

3. 알림 **규칙 저장을 클릭합니다.**

## <a name="delete-notification-rule"></a>알림 규칙 삭제

1. 삭제할 알림 규칙을 선택합니다.

2. **삭제** 를 클릭합니다.

## <a name="troubleshoot-email-notifications-for-alerts"></a>경고에 대한 전자 메일 알림 문제 해결

이 섹션에는 경고에 대한 전자 메일 알림을 사용할 때 발생할 수 있는 다양한 문제가 나열됩니다.

**문제:** 의도한 받는 사람은 알림을 받고 있지 않다고 보고합니다.

**해결 방법:** 알림이 전자 메일 필터에 의해 차단되지 않는지 확인:

1. 끝점용 Defender 전자 메일 알림이 정크 메일 폴더로 전송되지 않는지 확인합니다. 정크 아님으로 표시
2. 전자 메일 보안 제품이 끝점용 Defender의 전자 메일 알림을 차단하지 않는지 확인
3. 끝점 전자 메일 알림을 위해 Defender를 catch하고 이동하고 있을 수 있는 전자 메일 응용 프로그램 규칙을 검사합니다.

## <a name="related-topics"></a>관련 항목

- [데이터 보존 설정 업데이트](data-retention-settings.md)
- [고급 기능 구성](advanced-features.md)
- [끝점용 Microsoft Defender에서 취약성 전자 메일 알림 구성](/microsoft-365/security/defender-endpoint/configure-vulnerability-email-notifications)
