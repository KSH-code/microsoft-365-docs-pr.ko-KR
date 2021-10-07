---
title: 웹 에지에서 Microsoft Viva Learning(미리 보기)에 대한 학습 콘텐츠 원본 Microsoft 365 관리 센터
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
ms.localizationpriority: ''
description: 앱의 미리 보기(미리 보기)에 Microsoft Viva Learning 학습 콘텐츠 원본을 구성하는 Microsoft 365 관리 센터.
ms.openlocfilehash: 3161841f3c69992d7cc532e86f99bed7704ba016
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208172"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a>웹 에지에서 Microsoft Viva Learning(미리 보기)에 대한 학습 콘텐츠 원본 Microsoft 365 관리 센터

> [!NOTE]
> 이 문서의 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 보기 제품과 관련이 있습니다. 

조직의 관리자는 Microsoft 365 관리 센터 또는 조직에서 선택한 개인에게 기술 관리자 역할을 할당하여 Viva Learning(미리 보기)와 관련된 설정을 관리하고 학습 콘텐츠 원본을 구성할 수 있습니다.

관리자는 Viva SharePoint(미리 보기) 사용자가 사용할 다른 학습 콘텐츠 원본(예: SharePoint 또는 지원되는 타사 콘텐츠 공급자 원본)을 Learning 선택합니다. 그런 다음 관리자는 해당 원본을 구성하여 콘텐츠를 검색 및 검색에 사용할 수 있으며 Viva Learning(미리 보기)를 사용하는 직원이 검색할 수 있습니다.

> [!NOTE]
>  사용자는 브라우저 또는 포함된 뷰어에서 학습을 Learning Pro Microsoft가 아닌 다른 사용자 및 LinkedIn에 로그인합니다. 이 구성된 학습은 Viva Learning(미리 보기) 약관이 아니라 조직과 제3자 간의 별도의 사용권, 개인 정보 보호 및 서비스 약관의 적용을 하게 됩니다. 이 유형의 학습을 선택하기 전에 조직 및 사용자에 대한 계약이 있는지 확인해야 합니다.

## <a name="assign-the-knowledge-admin-role-optional"></a>지식 관리자 역할 할당(선택 사항)

이러한 작업을 수행하려면 Microsoft 365 전역 관리자 되어야 합니다.

> [!TIP]
> 지식 관리자는 보통 기술적인 지식이 있으며 기존 SharePoint 자격 증명(조직의 교육, 학습, 교육 또는 직원 경험에 잘 학습된 사용자)이 있는 것이 바람직합니다.

### <a name="add-a-knowledge-admin"></a>지식 관리자 추가

Viva Learning(미리 보기)에 대한 지식 관리자를 추가하려면 다음 단계를 따릅니다.

1. 사이트 모음의 왼쪽 탐색 Microsoft 365 관리 센터 **역할로 이동합니다.**

2. 역할 **페이지의** Azure AD **탭에서** 기술 관리자 **를 선택합니다.**
 
3. 기술 **관리자 패널에서** 할당된 **관리자를** 선택하고 추가 를 **선택합니다.**

     ![사용자 추가를 Microsoft 365 관리 센터 기술 관리자 패널을 표시하는 목록의 역할 페이지입니다.](../media/learning/learning-add-knowledge-admin-1.png)

3. 관리자 **추가 패널에서** 역할에 대해 선택한 사람을 선택하고 추가 를 **선택합니다.**

     ![사용자 추가를 Microsoft 365 관리 센터 관리자 추가 패널을 표시하는 페이지의 역할 페이지입니다.](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a>지식 관리자 제거

Viva Learning(미리 보기)에 대한 지식 관리자를 제거하려면 다음 단계를 수행합니다.

1. 사이트 모음의 왼쪽 탐색 Microsoft 365 관리 센터 **역할로 이동합니다.**

2. 역할 **페이지의** Azure AD **탭에서** 기술 관리자 **를 선택합니다.**
 
3. 지식 **관리자 패널의** 할당된 관리자  **탭에서** 제거 를 선택한 다음 역할에서 제거할 사람을 선택합니다. 확인하려면 제거 를 **선택합니다.**

     ![사용자 제거를 Microsoft 365 관리 센터 할당된 관리자 패널을 표시하는 페이지의 역할 페이지입니다.](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a>학습 콘텐츠 원본에 대한 설정 구성

이러한 작업을 수행하려면 Microsoft 365 관리자 또는 지식 관리자 되어야 합니다.

Viva 2013에서 콘텐츠 원본을 학습하기 위한 설정을 Learning 다음 단계를 따르세요.

1. 사이트 모음의 왼쪽 탐색 Microsoft 365 관리 센터 로 이동하여 설정  >  **로 이동합니다.**

2. Org **설정 페이지의** 서비스 **탭에서** **Viva Learning(미리 보기)를 선택합니다.**

     ![설정 앱을 표시하는 Microsoft 365 관리 센터 페이지의 Learning 표시됩니다.](../media/learning/learning-sharepoint-configure1.png)

3. **Viva Learning(미리 보기)** 패널에서 조직에 대해 구성할 학습 콘텐츠 원본을 선택한 다음 저장을 **선택합니다.**

     ![Learning 원본 옵션을 표시하는 Microsoft 365 관리 센터 패널입니다.](../media/learning/learning-sharepoint-configure2.png)

존재하는 모든 학습 소스 중에서 일부는 기본적으로 사용하도록 설정됩니다. 이러한 학습 원본은 다음과 같습니다.

- LinkedIn Learning(무료 콘텐츠)
- Microsoft Learn
- Microsoft 365 교육

> [!NOTE]
> LinkedIn 무료 콘텐츠는 LinkedIn 개인 정보 취급 방침 및 사용자 계약에 따라 사용자에게 제공됩니다. LinkedIn은 사용자의 IP 주소, 이전에 LinkedIn에서 설정한 쿠키를 수신하며 무료 콘텐츠 사용을 추적하기 위해 새 쿠키를 설정할 것입니다. 사용자는 무료 콘텐츠를 받기 위해 LinkedIn에 로그인할 필요는 없습니다.<br><br>
LinkedIn 프리미엄 콘텐츠의 경우 조직에서 해당 콘텐츠에 액세스하려면 팀의 구독이 필요합니다. 사용자는 LinkedIn을 통해 조직 및 사용자 약관에 따라 제공되는 학습에 액세스하려면 LinkedIn에 로그인해야 합니다.<br><br> Microsoft가 아닌 콘텐츠(무료 LinkedIn 콘텐츠 제외)의 경우 조직에서 Viva 계정(미리 보기)에 연결하기 전에 사용자가 작업 계정을 사용하여 해당 콘텐츠에 액세스할 수 있는 구독이 Learning 합니다. Microsoft가 아닌 학습 공급자에 대한 사용자의 개인 구독은 Viva Learning(미리 보기)와 통합되지 않습니다. 사용자는 브라우저 또는 포함된 뷰어에서 학습을 Learning Pro Microsoft가 아닌 다른 사용자 및 LinkedIn에 로그인합니다. 사용자가 조직 구독이 없는 콘텐츠로 이동하면 개별 구독에 등록할 수 있는 공급자 페이지가 표시될 수 있습니다. Microsoft가 아닌 모든 학습은 Viva 공급자의 일부가 아니라 Microsoft가 아닌 공급자의 약관에 따라 Learning. 

학습 콘텐츠 원본을 사용하도록 설정하거나 사용하지 않도록 설정하려면 원본 옆의 확인란을 선택합니다. 원본을 사용하도록 설정하면 확인 표시가 표시됩니다.

## <a name="third-party-content-providers"></a>타사 콘텐츠 공급자 

사용 가능한 연결된 학습 공급자 집합은 변경될 수 있습니다. 프로그램이 커질수록 더 많은 공급자가 참여하게 됩니다. 사용 가능한 공급자가 Viva 또는 Viva(미리 보기)와의 연결을 Learning 있습니다.

### <a name="skillsoft-as-a-content-source"></a>콘텐츠 원본으로 기술  

Viva Learning(미리 보기)의 경우 Skillsoft를 사용하도록 설정하고 Skillsoft 콘텐츠를 보기로 선택한 사용자는 조직의 Percipio 사이트 이름을 입력할지 묻는 Percipio 페이지에 표시됩니다. 사용자가 조직의 사이트 이름을 입력하면 조직의 Percipio 사이트에 로그인하기 위해 페이지로 이동됩니다. 사용자는 기존 자격 증명을 사용하여 로그인하고 원래 선택한 콘텐츠를 볼 수 있습니다. 사용자는 브라우저 캐시가 지워질 때까지 Percipio 사이트 이름을 한 번만 입력해야 합니다. 사용자에 대해 이 환경을 간소화하기 위해 Viva Learning(미리 보기)에 보내는 내부 통신에 Percipio 사이트 이름을 Learning 좋습니다.

이는 미리 보기를 위한 임시 환경으로, 사용자가 조직의 Percipio 사이트 이름을 제공해야 하는 단계를 우회하는 일반 가용성을 위해 테넌트별 통합을 지원하기 위해 Skillsoft와 협력하고 있습니다. 

### <a name="details-on-microsoft-substrate"></a>Microsoft 기판에 대한 세부 정보  

Microsoft가 아닌 서비스(학습 공급자 또는 학습 관리 시스템)에서 Viva Learning(미리 보기)로 복사하는 데이터의 경우 Viva Learning(미리 보기)에서 해당 데이터를 직접 추출, 수정 또는 삭제할 수 없습니다. Microsoft가 아닌 다른 공급자에서 가져온 데이터를 즉시 새로 고쳐 Microsoft가 아닌 원본 데이터의 변경 내용과 변경 내용을 반영합니다.

Microsoft가 아닌 서비스의 라이선스, 서비스 또는 개인 정보 취급 방침에 따라 데이터를 액세스, 수정, 삭제 또는 추출하려면 Microsoft가 아닌 서비스 공급업체와 협력해야 합니다. 이 변경 내용은 Microsoft가 아닌 서비스 및 Viva Learning(미리 보기)의 데이터 업데이트 주기가 완료될 때 Viva Learning(미리 보기)에서 사용하기 위해 처리된 데이터에 반영됩니다. Viva Learning(미리 보기)와 Microsoft가 아닌 서비스 간의 연결을 끄면 이전에 해당 서비스에서 가져온 모든 데이터가 삭제됩니다. 

## <a name="next-step"></a>다음 단계

[SharePoint 학습 콘텐츠 원본으로 구성(Microsoft Viva Learning)](configure-sharepoint-content-source.md)