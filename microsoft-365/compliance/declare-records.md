---
title: 보존 레이블을 사용하여 레코드 선언
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 보존 레이블을 사용하여 레코드 선언
ms.openlocfilehash: d637817e8d1bcc8c72bfe011dfd288ac4e2d0298
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778518"
---
# <a name="declare-records-by-using-retention-labels"></a>보존 레이블을 사용하여 레코드 선언

>*[보안 및 규정 준수에 대한 Microsoft 365 라이센스 지침](https://aka.ms/ComplianceSD)입니다.*

항목을 레코드로 선언하려면 콘텐츠를 레코드로 표시하는 [보존 레이블](retention.md#retention-labels)을 사용합니다. 사용자 및 관리자가 콘텐츠에 직접 적용할 수 있도록 해당 레이블을 게시하거나 레코드로 표시하기를 원하는 콘텐츠에 해당 레이블을 자동으로 적용할 수 있습니다.

## <a name="configuring-retention-labels-to-declare-records"></a>레코드를 선언하도록 보존 레이블을 구성 중

보존 레이블을(를) 생성하거나 구성할 때 콘텐츠를 레코드로 표시하는 옵션을 선택합니다.

>[!NOTE] 
> Microsoft 365 규정 준수 센터의 **정보 거버넌스**에서 보존 레이블을 생성하거나 구성하는 경우에는 내용을 레코드로 표시하는 옵션을 사용할 수 없습니다. 대신 **레코드 관리**를 사용해야 합니다.

콘텐츠를 레코드로 표시하는 새 보존 레이블을 만들려면 다음을 수행합니다.

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)에서 **관리 기록** \> **파일 계획**(으)로 이동합니다. **파일 계획** 페이지에서 **레이블 만들기**를 선택합니다.

2. 마법사의 **레이블 설정** 페이지에서 콘텐츠를 레코드로 분류하는 옵션을 선택합니다.
    
   ![레이블을 사용하여 콘텐츠를 레코드로 분류 확인란을 클릭합니다.](../media/recordversioning6.png)

3. 필요에 따라 SharePoint 또는 OneDrive 문서와 Exchange 전자 메일에 보존 레이블을 적용합니다. 해당 지침은 다음 항목을 참조하세요.
    
    - [보존 레이블을 만들고 앱에 적용하기](create-apply-retention-labels.md)
    
    - [보존 레이블을 콘텐츠에 자동으로 적용하기](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a>콘텐츠에 구성된 보존 레이블 적용

콘텐츠를 레코드로 표시하는 보존 레이블을 사용자가 앱에 적용할 수 있도록 설정한 경우:

- Exchange의 경우 사서함에 대한 쓰기 권한이 있는 사용자는 이러한 레이블을 적용할 수 있습니다. 
- SharePoint 및 OneDrive의 경우 기본 구성원 그룹에 있는 모든 사용자(참가 권한 수준)는 이러한 레이블을 적용할 수 있습니다.

보존 레이블을 사용하여 레코드로 표시된 문서 예제:

![레코드로 태그가 지정된 문서에 대한 세부 정보 창](../media/recordversioning7.png)

## <a name="next-steps"></a>다음 단계

레코드 관리에서 지원되는 기타 시나리오 목록은 [레코드 관리에 대한 일반적인 시나리오](get-started-with-records-management.md#common-scenarios-for-records-management)를 참조하세요.
