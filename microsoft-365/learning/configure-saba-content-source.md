---
title: 사바를 콘텐츠 원본으로 Microsoft Viva Learning
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/27/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: Saba를 사용자용 학습 콘텐츠 원본으로 구성하는 Microsoft Viva Learning.
ms.openlocfilehash: cb13822e2f4a0a2eccf31e2c03f2ac5e109dd843
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950500"
---
# <a name="configure-saba-as-a-content-source-for-microsoft-viva-learning"></a>사바를 콘텐츠 원본으로 Microsoft Viva Learning

이 문서에서는 Saba를 사용자용 타사 학습 콘텐츠 원본으로 구성하는 Microsoft Viva Learning. 이러한 단계를 수행하려면 Saba 시스템 관리자 또는 Super User가 되어야 합니다.

>[!NOTE]
>Viva Learning 액세스할 수 있는 콘텐츠에는 Microsoft 제품 약관이 없는 약관이 적용될 수 있습니다. Saba 콘텐츠 및 관련 서비스는 Saba의 개인 정보 및 서비스 약관을 준수합니다.

>[!NOTE]
>Viva Learning Saba와의 통합은 월별 API 호출 버킷의 API를 사용하며 제한 한도에 계산됩니다.

## <a name="configure-in-your-saba-portal"></a>사바 포털에서 구성

>[!NOTE]
>이 단계를 완료하려면 사바에서 관리자 권한이 필요합니다.

### <a name="clients-host-url"></a>클라이언트의 호스트 URL

1. 기본 Saba 클라우드 URL(예: "org".sabacloud.com)을 식별합니다. API 대시보드 URL이 org-api.sabacloud.com 호스트 URL이 org.sabacloud.com.
2. **Saba** Cloud Admin System Admin Manage Integrations API Dashboard로 이동하여 API 대시보드  >    >    >    >  **URL을 식별합니다.** API 대시보드 URL을 찾은 다음 호스트 URL을 https:// "https://" 및 "-api"를 제거합니다.

    ![API 대시보드의 이미지입니다.](../media/learning/saba-a.png)

### <a name="client-id-and-client-secret"></a>클라이언트 ID 및 클라이언트 비밀

1. 호스트 URL이 있는 동일한 화면에서 클라이언트 ID 및 클라이언트 비밀이 이미 생성된 경우 복사합니다.

2. 클라이언트 비밀이 아직 없는 경우 **GENERATE** 단추를 선택하여 생성합니다.

    ![생성 단추를 마우스로 이동하는 커서가 있는 API 대시보드의 이미지입니다.](../media/learning/saba-b.png)

## <a name="configure-in-your-microsoft-365-admin-center"></a>사용자 설정에서 Microsoft 365 관리 센터

사용자 설정에서 구성을 완료해야 Microsoft 365 관리 센터.

>[!NOTE]
>이러한 단계를 완료하려면 관리자 권한이 Microsoft 365 합니다.

1. 에 [로그인합니다Microsoft 365 관리 센터.](https://admin.microsoft.com)
2. 다음 **설정** **로 이동합니다.** Viva Learning 선택하고 패널에서 사바 클라우드를 사용하도록 설정합니다.
3. Saba 포털에서 확인한 세부 정보를 입력합니다.
    >[!NOTE]
    >표시 이름은 Viva 2013에서 조직의 사용자에게 Saba 학습 콘텐츠가 표시될 수 있는 Learning. 새 이름을 입력하지 않은 경우 기본 이름 "Saba Cloud"가 표시됩니다.
4. 저장을 **선택하여** 저장에서 사바 클라우드 콘텐츠를 Microsoft Viva Learning. Viva 365에 콘텐츠를 표시하는 데 최대 24시간이 걸릴 Learning.

> [!Note]
> Saba Cloud 통합의 경우 호스트 URL에 sabacloud.com 도메인이 필요합니다. 다른 도메인 이름이 있는 경우 도메인 이름을 허용하기 위해 지원 티켓을 발생해야 합니다.

>[!NOTE]
>현재 조직 내의 모든 사용자는 모든 테넌트 관련 과정을 검색할 수 있지만 액세스 권한이 있는 과정만 사용할 수 있습니다. 역할 및 사용 권한을 기반으로 하는 사용자별 콘텐츠 검색은 향후 릴리스될 예정입니다.
