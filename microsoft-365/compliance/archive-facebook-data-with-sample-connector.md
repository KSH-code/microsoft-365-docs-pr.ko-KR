---
title: Facebook 데이터를 보관할 커넥터 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Microsoft 365 & 센터에서 커넥터를 사용하여 Facebook 비즈니스 페이지에서 Microsoft 365로 & 보관 데이터를 가져오는 방법을 학습합니다.
ms.openlocfilehash: db1d11f461125e7ea1d749fd273f8bc8622a8d77
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620435"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Facebook 데이터를 보관할 커넥터 설정(미리 보기)

Microsoft 365 규정 준수 센터의 커넥터를 사용하여 Facebook 비즈니스 페이지에서 Microsoft 365로 데이터를 가져오고 보관합니다. 커넥터를 설정하고 구성한 후 일정에 따라 Facebook 비즈니스 페이지에 연결하고 Facebook 항목의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 이러한 항목을 Microsoft 365의 사서함으로 가져올 수 있습니다.

Facebook 데이터를 가져온 후 소송 보존, 콘텐츠 검색, In-Place 보관, 감사, 커뮤니케이션 규정 준수 및 Microsoft 365 보존 정책과 같은 Microsoft 365 규정 준수 기능을 Facebook 데이터에 적용할 수 있습니다. 예를 들어 사서함에 소송 보존이 적용되거나 보존 정책에 할당된 경우 Facebook 데이터는 보존됩니다. 콘텐츠 검색을 사용하여 타사 데이터를 검색하거나 Facebook 데이터가 저장된 사서함을 Advanced eDiscovery 사례의 보호자와 연결할 수 있습니다. 커넥터를 사용하여 Microsoft 365에서 Facebook 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Facebook 비즈니스 페이지에 대한 커넥터를 설정하기 위한 선행 준비

조직의 Facebook 비즈니스 페이지에서 데이터를 가져오고 보관할 커넥터를 Microsoft 365 규정 준수 센터에서 설정하고 구성하기 전에 다음 선행 작업을 완료합니다. 

- 조직의 비즈니스 페이지에 대한 Facebook 계정이 필요합니다(커넥터를 설정할 때 이 계정에 로그인해야 합니다). 현재 Facebook 비즈니스 페이지에서만 데이터를 보관할 수 있습니다. 개별 Facebook 프로필에서 데이터를 보관할 수 없습니다.

- 조직에 유효한 Azure 구독이 있어야 합니다. 기존 Azure 구독이 없는 경우 다음 옵션 중 하나를 등록할 수 있습니다.

    - [1년 무료 Azure 구독에 등록](https://azure.microsoft.com/free) 

    - [Pay-As-You-Go Azure 구독에 등록](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Microsoft 365 구독에 포함된 [무료 Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) 구독은 보안 및 준수 센터에서 커넥터를 & 않습니다.

- Microsoft 365 규정 준수 센터(5단계)에서 사용자 지정 커넥터를 설정하는 사용자에게 Exchange Online의 사서함 가져오기 내보내기 역할이 할당되어야 합니다. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서에서 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하십시오.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>1단계: Azure Active Directory에서 앱 만들기

첫 번째 단계는 AAD(Azure Active Directory)에 새 앱을 등록하는 것입니다. 이 앱은 Facebook 커넥터에 대해 4단계 및 5단계에서 구현하는 웹 앱 리소스에 해당합니다. 

단계별 지침은 [Azure Active Directory에서 앱 만들기를 참조하세요.](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)

이 단계를 완료하는 동안(이전 단계별 지침 사용) 텍스트 파일에 다음 정보를 저장합니다. 이러한 값은 배포 프로세스의 이후 단계에서 사용됩니다.

- AAD 응용 프로그램 ID

- AAD 응용 프로그램 비밀

- 테넌트 ID

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>2단계: GitHub에서 Azure 계정으로 커넥터 웹 서비스 배포

다음 단계는 Facebook API를 사용하여 Facebook 계정에 연결하고 Microsoft 365로 가져올 수 있도록 데이터를 추출하는 Facebook 비즈니스 페이지 커넥터 앱의 소스 코드를 배포하는 것입니다. 조직에 배포하는 Facebook 커넥터는 Facebook 비즈니스 페이지의 항목을 이 단계에서 만든 Azure Storage 위치로 업로드합니다. Microsoft 365 규정 준수 센터(5단계)에서 Facebook 비즈니스 페이지 커넥터를 만든 후 가져오기 서비스는 Azure Storage 위치에서 Microsoft 365 조직의 사서함으로 Facebook 비즈니스 페이지 데이터를 복사합니다. [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) 섹션에서 설명한 것 처럼 Azure Storage 계정을 만들 수 있는 유효한 Azure 구독이 있어야 합니다.

단계별 지침은 [GitHub에서 Azure](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)계정으로 커넥터 웹 서비스 배포를 참조하세요.

이 단계를 완료하기 위한 단계별 지침에서는 다음 정보를 제공합니다.

- APISecretKey: 이 단계를 완료하는 동안 이 비밀을 생성합니다. 5단계에서 사용됩니다.

- TenantId: 1단계에서 Azure Active Directory에서 Facebook 커넥터 앱을 만들고 복사한 Microsoft 365 조직의 테넌트 ID입니다.

이 단계를 완료한 후 Azure 앱 서비스 URL(예: https://fbconnector.azurewebsites.net) 이 URL을 사용하여 3단계, 4단계 및 5단계를 완료해야 합니다.

## <a name="step-3-register-the-web-app-on-facebook"></a>3단계: Facebook에서 웹앱 등록

다음 단계는 Facebook에서 새 앱을 만들고 구성하는 것입니다. 5단계에서 만든 Facebook 비즈니스 페이지 커넥터는 Facebook 웹앱을 사용하여 Facebook API와 상호 작용하여 조직의 Facebook 비즈니스 페이지에서 데이터를 얻습니다.

단계별 지침은 Facebook 앱 [등록을 참조하세요.](deploy-facebook-connector.md#step-3-register-the-facebook-app)

이 단계를 완료하는 동안(단계별 지침에 따라) 텍스트 파일에 다음 정보를 저장합니다. 이러한 값은 4단계에서 Facebook 커넥터 앱을 구성하는 데 사용됩니다.

- Facebook 응용 프로그램 ID

- Facebook 응용 프로그램 비밀

- Facebook webhook은 토큰 확인

## <a name="step-4-configure-the-facebook-connector-app"></a>4단계: Facebook 커넥터 앱 구성

다음 단계는 1단계에서 Azure Web App 리소스를 만들 때 업로드한 Facebook 커넥터 앱에 구성 설정을 추가하는 것입니다. 이 작업을 위해 커넥터 앱의 홈 페이지로 이동하여 구성합니다.

단계별 지침은 Facebook 커넥터 앱 [구성을 참조하세요.](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)

이 단계를 완료하는 동안(단계별 지침에 따라) 이전 단계를 완료한 후 텍스트 파일에 복사한 다음 정보를 제공합니다.

- Facebook 응용 프로그램 ID(3단계에서 획득)

- Facebook 응용 프로그램 비밀(3단계에서 획득)

- Facebook webhook은 토큰 확인(3단계에서 획득)

- Azure Active Directory 응용 프로그램 ID(1단계에서 얻은 AAD 응용 프로그램 ID)

- Azure Active Directory 응용 프로그램 비밀(1단계에서 얻은 AAD 응용 프로그램 비밀)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>5단계: Microsoft 365 규정 준수 센터에서 Facebook 비즈니스 페이지 커넥터 설정

마지막 단계는 Facebook 비즈니스 페이지의 데이터를 Microsoft 365의 지정된 사서함으로 가져올 커넥터를 Microsoft 365 규정 준수 센터에서 설정하는 것입니다. 이 단계를 완료하면 Microsoft 365 가져오기 서비스가 Facebook 비즈니스 페이지에서 Microsoft 365로 데이터를 가져오기 시작하게 됩니다.

단계별 지침은 Microsoft 365 규정 준수 센터에서 Facebook 커넥터 설정 [5단계를 참조하세요.](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center) 

이 단계를 완료하는 동안(단계별 지침에 따라) 다음 정보를 제공합니다(단계를 완료한 후 텍스트 파일에 복사).

- AAD 응용 프로그램 ID(1단계에서 획득)

- Azure 앱 서비스 URL(예: 1단계에서 획득) https://fbconnector.azurewebsites.net)

- APISecretKey(2단계에서 만든 APISecretKey)
