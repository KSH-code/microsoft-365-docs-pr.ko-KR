---
title: Twitter 데이터를 보관할 커넥터 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 관리자가 네이티브 커넥터를 설정 하 고 사용 하 여 Twitter 데이터를 Microsoft 365로 가져오는 방법에 대해 알아봅니다.
ms.openlocfilehash: ba6c0786c0861776bad00dc1ed8f859da378a355
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818427"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>Twitter 데이터를 보관 하는 연결선 설정 (미리 보기)

Microsoft 365 준수 센터의 커넥터를 사용 하 여 Twitter에서 Microsoft 365로 데이터를 가져오고 보관 합니다. 커넥터를 설정 하 고 구성한 후에는 일정에 따라 조직의 Twitter 계정에 연결 하 고, 항목의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 Microsoft 365의 사서함으로 가져옵니다.

Twitter 데이터를 가져온 후에는 소송 보존, 콘텐츠 검색, 원본 위치 보관, 감사 및 Microsoft 365 고정 정책 등의 Microsoft 365 준수 기능을 Twitter 데이터에 적용할 수 있습니다. 예를 들어, 사서함을 소송 보존으로 설정 하는 경우에는 Twitter 데이터가 보존 됩니다. 콘텐츠 검색을 사용 하 여 타사 데이터를 검색 하거나, 고급 eDiscovery 사례에서 Twitter 데이터가 custodian와 함께 저장 된 사서함을 연결할 수 있습니다. 커넥터를 사용 하 여 Microsoft 365에서 Twitter 데이터를 가져오고 보관 하면 조직이 정부 및 규정 정책을 준수 하는 데 도움이 될 수 있습니다.

Twitter 데이터를 가져온 후에는 사서함에 저장 된 데이터에 소송 보존, 콘텐츠 검색, 원본 위치 보관, 감사, 통신 준수 및 Microsoft 365 고정 정책 등의 Microsoft 365 준수 기능을 적용할 수 있습니다. 예를 들어 콘텐츠 검색을 사용 하 여 Twitter 데이터를 검색 하거나, 데이터가 고급 eDiscovery 사례에 custodian으로 저장 된 사서함을 연결할 수 있습니다. 커넥터를 사용 하 여 Microsoft 365에서 Twitter 데이터를 가져오고 보관 하면 조직이 정부 및 규정 정책을 준수 하는 데 도움이 될 수 있습니다.

## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a>Twitter에 대 한 커넥터를 설정 하기 위한 필수 구성 요소

Microsoft 365 준수 센터에서 커넥터를 설정 및 구성 하 여 조직의 Twitter 계정에서 데이터를 가져오고 보관 하려면 먼저 다음 필수 구성 요소를 완료 합니다.

- 조직에 대 한 Twitter 계정이 필요 합니다. 커넥터를 설정 하는 경우이 계정에 로그인 해야 합니다.

- 조직에 유효한 Azure 구독이 있어야 합니다. 기존 Azure 구독이 없는 경우 다음 옵션 중 하나를 등록할 수 있습니다.

    - [무료 1 년간 Azure 구독 등록](https://azure.microsoft.com/free) 

    - [방문 비용 청구 Azure 구독에 등록](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Microsoft 365 구독에 포함 된 [무료 Azure Active Directory 구독은](use-your-free-azure-ad-subscription-in-office-365.md) 보안 & 준수 센터의 커넥터를 지원 하지 않습니다.

- 조직에서는 Office 365 가져오기 서비스가 조직의 사서함 데이터에 액세스할 수 있도록 허용 해야 합니다. 이 요청에 동의 하려면 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)이동 하 여 전역 관리자의 자격 증명으로 로그인 한 다음 요청을 수락 합니다.

- Microsoft 365 준수 센터에서 Twitter 커넥터를 설정 하는 사용자에 게 Exchange Online의 사서함 가져오기 내보내기 역할이 할당 되어야 합니다. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>1 단계: Azure Active Directory에 앱 만들기

첫 번째 단계는 AAD (Azure Active Directory)에서 새 앱을 등록 하는 것입니다. 이 앱은 Twitter 커넥터에 대해 2 단계에서 구현 하는 웹 앱 리소스에 해당 합니다.

단계별 지침은 [Azure Active Directory에서 앱 만들기](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)를 참조 하세요.

단계별 지침에 따라이 단계를 완료 하는 동안 다음 정보를 텍스트 파일에 저장 합니다. 이러한 값은 배포 프로세스의 이후 단계에서 사용 됩니다.

- AAD 응용 프로그램 ID

- AAD 응용 프로그램 비밀

- 테 넌 트 Id

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>2 단계: GitHub 리포지토리에서 커넥터 웹 서비스를 Azure 계정으로 배포

다음 단계에서는 Twitter API를 사용 하 여 twitter 계정에 연결 하 고 데이터를 추출 하 여 Microsoft 365로 가져올 수 있는 Twitter 커넥터 응용 프로그램에 대 한 소스 코드를 배포 합니다. 조직에 대해 배포 하는 Twitter 커넥터는 조직의 Twitter 계정에서이 단계에서 만든 Azure 저장소 위치로 항목을 업로드 합니다. Microsoft 365 준수 센터 (5 단계)에서 Twitter 커넥터를 만든 후에는 Office 365 가져오기 서비스가 Azure Storage 위치에서 Twitter 데이터를 Microsoft 365의 사서함으로 복사 합니다. 앞에서 설명한 것 처럼 [필수 구성 요소](#prerequisites-for-setting-up-a-connector-for-twitter) 섹션에서 azure Storage 계정을 만들려면 유효한 azure 구독이 있어야 합니다.

Twitter 커넥터 응용 프로그램에 대 한 소스 코드를 배포 하려면:

1. [이 GitHub 사이트로](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)이동 합니다.

2. **Azure에 배포를**클릭 합니다.

단계별 지침은 [GitHub의 커넥터 웹 서비스를 Azure 계정에 배포](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)를 참조 하세요.

단계별 지침에 따라이 단계를 완료 하는 동안 다음 정보를 제공 합니다.

- APISecretKey:이 단계를 완료 하는 동안이 비밀을 만듭니다. 5 단계에서 사용 됩니다.

- tenantId: 1 단계에서 Azure Active Directory에 Twitter 앱을 만든 후 복사한 Microsoft 365 조직의 테 넌 트 ID입니다.

이 단계를 완료 한 후에는 앱 서비스 URL (예:)을 복사 해야 `https://twitterconnector.azurewebsites.net` 합니다. 이 URL을 사용 하 여 3 단계, 4 단계, 5 단계를 완료 해야 합니다.

## <a name="step-3-create-developer-app-on-twitter"></a>3 단계: Twitter에서 개발자 앱 만들기

다음 단계에서는 Twitter에서 개발자 앱을 만들고 구성 합니다. 7 단계에서 만든 사용자 지정 커넥터는 twitter 앱을 사용 하 여 Twitter API와 상호 작용 하 여 조직의 Twitter 계정에서 데이터를 가져옵니다.

단계별 지침은 [Twitter 앱 만들기](deploy-twitter-connector.md#step-3-create-the-twitter-app)를 참조 하세요.

단계별 지침에 따라이 단계를 완료 하는 동안 다음 정보를 텍스트 파일에 저장 합니다. 이러한 값은 4 단계에서 Twitter 커넥터 응용 프로그램을 구성 하는 데 사용 됩니다.

- Twitter API 키

- Twitter API 비밀 키

- Twitter 액세스 토큰

- Twitter 액세스 토큰 암호

## <a name="step-4-configure-the-twitter-connector-app"></a>4 단계: Twitter 커넥터 응용 프로그램 구성

다음 단계에서는 2 단계에서 배포한 Twitter 커넥터 앱에 구성 설정을 추가 합니다. 이렇게 하려면 커넥터 응용 프로그램의 홈 페이지로 이동 하 여 구성 합니다.

단계별 지침은 [Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)을 참조 하십시오.

단계별 지침에 따라이 단계를 완료 하는 동안 이전 단계를 완료 한 후에 텍스트 파일로 복사한 다음 정보를 제공 합니다.

- Twitter API 키 (3 단계에서 가져옴)

- Twitter API 비밀 키 (3 단계에서 가져옴)

- Twitter 액세스 토큰 (3 단계에서 가져옴)

- Twitter 액세스 토큰 암호 (3 단계에서 가져옴)

- Azure Active Directory 응용 프로그램 ID (1 단계에서 가져온 AAD 응용 프로그램 ID)

- Azure Active Directory 응용 프로그램 비밀 (1 단계에서 얻은 AAD 응용 프로그램 암호)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>5 단계: Microsoft 365 준수 센터에서 Twitter 커넥터 설정

마지막 단계에서는 조직의 Twitter 계정에서 Microsoft 365의 지정 된 사서함으로 데이터를 가져올 Microsoft 365 준수 센터에서 Twitter 커넥터를 설정 합니다. 이 단계를 완료 한 후에는 Office 365 가져오기 서비스가 조직의 Twitter 계정에서 Microsoft 365로 데이터 가져오기를 시작 합니다.

단계별 지침은 [Microsoft 365 준수 센터에서 Twitter 커넥터 설정을](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)참조 하십시오. 

단계별 지침에 따라이 단계를 완료 하는 동안 다음 정보를 제공 합니다 (단계 완료 후 텍스트 파일로 복사).

- Azure app service URL (예: 2 단계에서 가져옴 `https://twitterconnector.azurewebsites.net` )

- APISecretKey (2 단계에서 만든 것)
