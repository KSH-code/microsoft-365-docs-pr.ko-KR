---
title: 사용자용 다른 콘텐츠 공급자 Microsoft Viva Learning
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/22/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: 다른 공급자를 사용자에 대한 학습 콘텐츠 원본으로 구성하는 Microsoft Viva Learning.
ROBOTS: NOINDEX
ms.openlocfilehash: 006b3e6690df253f80bc8e47d93264b9bf19ea0f
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557272"
---
# <a name="add-other-content-providers-for-microsoft-viva-learning"></a>사용자용 다른 콘텐츠 공급자 Microsoft Viva Learning

Viva 및 Viva를 통해 점점 더 많은 학습 콘텐츠 공급자 및 학습 관리 시스템을 사용할 Learning. 이 집합은 더 많은 공급자가 프로그램에 참여하거나 프로그램을 통해 상태를 변경하면 변경될 수 있습니다.

타사 콘텐츠 원본은 기본적으로 사용하도록 설정되어 있지 않습니다. 이러한 원본을 사용하도록 설정하려면 [](content-sources-365-admin-center.md#configure-settings-for-the-learning-content-sources) 다음 표에 나와 있는 특정 Microsoft 365 관리 센터 추가해야 합니다.

|콘텐츠 공급자  |구성 지침  |
|---------|---------|
|Cornerstone OnDemand |[Cornerstone OnDemand를 콘텐츠 원본으로 구성](configure-cornerstone-content-source.md)         |
|Go1     |[Go1을 콘텐츠 원본으로 구성](configure-go1-content-source.md)         |
|사바    |[사바를 콘텐츠 원본으로 구성](configure-saba-content-source.md)         |
|Skillsoft     |[Skillsoft를 콘텐츠 원본으로 구성](configure-skillsoft-content-source.md)         |
|SAP SuccessFactors   |[SAP SuccessFactors를 콘텐츠 원본으로 구성](configure-successfactors-content-source.md)         |
|Udemy   |[Udemy를 콘텐츠 원본으로 구성](configure-udemy-content-source.md)         |

## <a name="content-ingestion-errors"></a>콘텐츠 검색 오류

콘텐츠가 검색되는 동안 Microsoft 365 관리 센터 발생하는 경우 다음 단계를 위해 아래 표를 참조하세요. 이 목록은 전체 목록으로, 향후 더 많은 오류 코드를 포함할 수 있습니다.

|콘텐츠 공급자 |오류 코드 |오류 코드 설명 |
|:----------------|:----------|:----------------------|
|모든 공급자 |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |제공한 인증 자격 증명이 잘못되었습니다. 올바른 자격 증명을 입력해야 합니다. 자세한 내용은 Microsoft 고객 지원에 문의할 수 있습니다. |
|모든 공급자 |USR_ERROR_ACCESS_DENIED |파트너의 액세스가 거부됩니다. 입력한 자격 증명이 올바른지 확인하거나 콘텐츠 공급자의 지원 팀에 문의하세요. |
|SuccessFactors |USR_ERROR_SFTP_NO_FILES_FOUND |SuccessFactors SFTP 서버에 파일이 없는 경우 새 콘텐츠가 검색되지 않습니다. |
|SuccessFactors |USR_ERROR_SF_PACKAGE_NOT_FOUND |SuccessFactors SFTP 서버에서 필수 패키지로 검색된 새 콘텐츠를 찾을 수 없습니다. |
|Cornerstone OnDemand |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |제공한 인증 자격 증명이 잘못되었습니다. Cornerstone OnDemand 포털의 Viva Learning 앱에서 자격 증명을 복사하는지 확인 |

## <a name="third-party-content-consumption"></a>타사 콘텐츠 사용

타사 콘텐츠 공급자를 Microsoft 365 관리 센터 콘텐츠 원본으로 추가하면 공급자의 콘텐츠가 Viva Learning 앱으로 흐르며 최종 사용자에게 표시됩니다.

사용자가 Viva Learning 강의를 재생하도록 선택하면 콘텐츠 공급자의 웹 페이지로 이동하고 공급자의 로그인 페이지에 로그인 자격 증명을 입력해야 합니다. [Viva 및 Viva를 통해](https://support.microsoft.com/office/viva-learning-preview-01bfed12-c327-41e0-a68f-7fa527dcc98a)콘텐츠를 사용 하는 방법에 대해 Learning.
