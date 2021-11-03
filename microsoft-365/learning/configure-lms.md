---
title: 사용자용 학습 관리 Microsoft Viva Learning
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 11/01/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: 학습 관리 시스템을 학습용 학습 콘텐츠 원본으로 구성하는 방법을 Microsoft Viva Learning.
ms.openlocfilehash: 84f2e0d50b36f7fe54d82db9fb5564dcbbcbe9fa
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60677275"
---
# <a name="add-learning-management-systems-for-microsoft-viva-learning"></a>사용자용 학습 관리 Microsoft Viva Learning

Viva 및 Viva를 통해 점점 더 많은 학습 관리 시스템 집합을 사용할 Learning. 이 집합은 더 많은 공급자가 프로그램에 참여하거나 프로그램을 통해 상태를 변경하면 변경될 수 있습니다.

Learning 관리 시스템은 기본적으로 사용하도록 설정되어 있지 않습니다. 이러한 원본을 사용하도록 설정하려면 [](content-sources-365-admin-center.md#configure-settings-for-the-learning-content-sources) 다음 표에 나와 있는 특정 Microsoft 365 관리 센터 추가해야 합니다.

>[!NOTE]
>학습 관리 시스템을 연결하려면 Premium 라이선스가 필요합니다. [라이선스에 대해 자세히 알아보시다.](https://www.microsoft.com/microsoft-viva/learning)

>[!NOTE]
>Viva 사용자가 관리 포털에서 사용하도록 설정한 Learning 콘텐츠를 보는 데 24~48시간이 걸릴 수 있습니다.

## <a name="learning-management-systems"></a>Learning 관리 시스템

|Learning 관리 시스템  |구성 지침  |
|---------|---------|
|Cornerstone OnDemand |[Cornerstone OnDemand를 콘텐츠 원본으로 구성](configure-cornerstone-content-source.md)         |
|사바    |[사바를 콘텐츠 원본으로 구성](configure-saba-content-source.md)         |
|SAP SuccessFactors   |[SAP SuccessFactors를 콘텐츠 원본으로 구성](configure-successfactors-content-source.md)         |

>[!NOTE]
>사용 가능한 학습 관리 시스템은 변경될 수 있습니다. 조직에 따라 여기에 나열된 다른 학습 관리 시스템에 액세스할 수 있습니다.

## <a name="content-ingestion-errors"></a>콘텐츠 검색 오류

콘텐츠가 검색되는 동안 Microsoft 365 관리 센터 발생하는 경우 다음 단계를 위해 아래 표를 참조하세요. 이 목록은 전체 목록으로, 향후 더 많은 오류 코드를 포함할 수 있습니다.

|Learning 관리 시스템 |오류 코드 |오류 코드 설명 |
|:----------------|:----------|:----------------------|
|모든 LMSs |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |제공한 인증 자격 증명이 잘못되었습니다. 올바른 자격 증명을 입력해야 합니다. 자세한 내용은 Microsoft 고객 지원에 문의할 수 있습니다. |
|모든 LMSs |USR_ERROR_ACCESS_DENIED |파트너의 액세스가 거부됩니다. 입력한 자격 증명이 올바른지 확인하거나 콘텐츠 공급자의 지원 팀에 문의하세요. |
|SuccessFactors |USR_ERROR_SFTP_NO_FILES_FOUND |SuccessFactors SFTP 서버에 파일이 없는 경우 새 콘텐츠가 검색되지 않습니다. |
|SuccessFactors |USR_ERROR_SF_PACKAGE_NOT_FOUND |SuccessFactors SFTP 서버에서 필수 패키지로 검색된 새 콘텐츠를 찾을 수 없습니다. |
|Cornerstone OnDemand |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |제공한 인증 자격 증명이 잘못되었습니다. Cornerstone OnDemand 포털의 Microsoft Viva Learning 자격 증명을 복사해야 합니다. |

## <a name="content-consumption-for-end-users"></a>최종 사용자의 콘텐츠 소비

학습 관리 시스템을 Microsoft 365 관리 센터 콘텐츠 원본으로 추가하면 LMS의 콘텐츠가 Viva Learning 앱으로 흐르며 최종 사용자에게 표시됩니다.

사용자가 Viva Learning 재생하도록 선택하면 LMS 웹 페이지로 이동하고 LMS 로그인 페이지에 로그인 자격 증명을 입력해야 합니다. [Viva 및 Viva를 통해](https://support.microsoft.com/office/01bfed12-c327-41e0-a68f-7fa527dcc98a)콘텐츠를 사용 하는 방법에 대해 Learning.
