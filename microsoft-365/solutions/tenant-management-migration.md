---
title: 4단계. 엔터프라이즈용 Microsoft 365 테넌트 마이그레이션
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Microsoft 365 테넌트에 대한 Windows 장치, Office 클라이언트 앱 및 Office 서버를 마이그레이션합니다.
ms.openlocfilehash: 85f1c0d927b881c4d1526ce538ae54f5954a0664
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406363"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>4단계. 엔터프라이즈용 Microsoft 365 테넌트 마이그레이션

대부분의 엔터프라이즈 조직에는 여러 릴리스의 운영 체제, 클라이언트 소프트웨어 및 서버 소프트웨어가 포함된 다른 환경이 있습니다. 엔터프라이즈용 Microsoft 365에는 IT 인프라의 주요 구성 요소 중 가장 안전한 버전이 포함되어 있습니다. 클라우드 기술을 활용하도록 설계된 생산성 기능도 포함되어 있습니다.

엔터프라이즈용 Microsoft 365 통합 제품군의 비즈니스 가치를 극대화하려면 다음 릴리스를 마이그레이션하는 전략을 계획하고 구현합니다.

| 시작 | 받는 사람 |
|:-------|:-----|
| Windows 7 및 Windows 8.1 | Windows 10 Enterprise |
| 직장의 장치에 설치된 Office 클라이언트 제품 | 엔터프라이즈용 Microsoft 365 앱 |
| Office server products installed on on-premises servers | Microsoft 365의 동등한 클라우드 기반 서비스 |
|  |  |

## <a name="migrating-to-windows-10"></a>Windows 10으로 마이그레이션

각 엔터프라이즈용 Microsoft 365 라이선스에는 Windows 10 Enterprise용 라이선스가 포함되어 있습니다. Windows 7 또는 Windows 8.1을 실행 하는 장치를 마이그레이션하려면 바로 업그레이드를 할 수 있습니다. *2020년 1월 14일* Windows 7에 대한 지원이 종료됩니다. 

전체 업그레이드를 넘어 Windows 10 Enterprise를 설치하는 추가 방법은 [Windows 10 배포 시나리오를 참조합니다.](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios) 직접 [Windows 10 배포를 계획](https://aka.ms/planforwin10deployment)할 수도 있습니다.

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱으로 마이그레이션

엔터프라이즈용 Microsoft 365에는 Microsoft 클라우드에서 설치 및 업데이트되는 Office 클라이언트 제품 버전(Word, PowerPoint, Excel 및 Outlook)인 엔터프라이즈용 Microsoft 365 앱이 포함되어 있습니다. 자세한 내용은 [엔터프라이즈용 Microsoft 365 앱 정보를 참조하세요.](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)

컴퓨터를 Office 2019 또는 이전 버전에 대해 최신으로 유지하는 대신 다음 단계를 수행합니다.

1. 사용자에 대한 Microsoft 365 라이선스를 다운로드하고 할당합니다.
2. 컴퓨터에서 Office 2013 또는 Office 2016을 제거합니다.
3. 개별적으로 또는 IT 롤아웃 중에 엔터프라이즈용 Microsoft 365 앱을 설치합니다. 자세한 내용은 Microsoft 365 앱 배포 [가이드를 참조하세요.](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

엔터프라이즈용 Microsoft 365 앱은 보안 업데이트와 새로운 기능 업데이트를 자동으로 설치하며 Microsoft 365의 클라우드 기반 서비스를 사용하여 향상된 보안 및 생산성을 활용할 수 있습니다.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>Microsoft 365로의 사내 서버 및 데이터 마이그레이션

엔터프라이즈용 Microsoft 365에는 웹 브라우저 및 Outlook 클라이언트와 같은 Office 서버 소프트웨어의 일부와 동일한 도구 중 일부를 사용하는 클라우드 기반 버전의 Office 서버 서비스가 포함되어 있습니다. 이러한 클라우드 기반 서비스는 보안 및 새 기능을 위해 자동으로 업데이트됩니다. 마이그레이션 후 IT 부서에서 사내 서버를 유지 관리하고 업데이트하는 데 걸리는 시간을 절약할 수 있습니다.

특정 Microsoft 365 워크로드에 대한 사용자 및 데이터를 마이그레이션하는 데 대한 정보는 다음 리소스를 사용합니다.

- [사서함을 Exchange Online으로 Exchange Server 사서함 이동](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [SharePoint Server에서 SharePoint Online으로 SharePoint 데이터 마이그레이션](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [비즈니스용 Skype Online을 Microsoft Teams로 마이그레이션](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>전체 조직 전환

전체 조직을 엔터프라이즈용 Microsoft 365의 제품 및 서비스로 이동하는 방법을 더 잘 확인하려면 다음 전환 포스터를 다운로드합니다.

[![Microsoft 365로 전환 포스터를 보여주는 이미지.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

이 두 페이지 포스터는 기존 인프라를 신속하게 인벤터리하는 방법입니다. 엔터프라이즈용 Microsoft 365에서 제품 또는 서비스로 이동하기 위한 지침을 얻습니다. Windows 및 Office 제품 및 기타 인프라 및 보안 요소(예: 장치 관리, ID 및 위협 방지, 정보 보호 및 규정 준수)를 보여줍니다.

## <a name="results-of-step-4"></a>4단계의 결과

Microsoft 365 테넌트에 대한 마이그레이션의 경우 다음을 결정했습니다.

- Windows 7 또는 Windows 8.1을 실행 중인 디바이스와 Windows 10 Enterprise로 업데이트할 계획입니다.
- Office 클라이언트 앱을 실행 중인 장치 및 엔터프라이즈용 Microsoft 365 앱으로 업데이트할 계획입니다.
- Microsoft 365에 해당하는 서비스로 마이그레이션해야 하는 사내 Office 서버 서비스와 해당 서비스 및 해당 데이터를 마이그레이션하기 위한 계획

다음은 전체 마이그레이션이 완료된 테넌트의 예입니다.

![완료된 마이그레이션을 완료한 테넌트의 예](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

이 그림에서 조직은 다음을 하게 됩니다.

- 해당 사서함의 Exchange Server Exchange Online으로 마이그레이션했습니다.
- Microsoft 365의 SharePoint로 해당 사내 SharePoint Server 사이트 및 데이터를 마이그레이션했습니다.

## <a name="ongoing-maintenance-for-migration"></a>마이그레이션을 위한 지속적인 유지 관리

지속적인 기준에 따라 다음을 해야 할 수 있습니다.

- Exchange 사서함 마이그레이션의 상태에 따라 Exchange Online으로의 전환을 조직에 계속 롤아웃합니다.
- 사내 SharePoint 사이트 마이그레이션의 상태에 따라 Microsoft 365의 SharePoint로의 전환을 조직에 계속 배포합니다.

## <a name="next-step"></a>다음 단계

[![5단계. 장치 및 앱 관리 배포](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

장치 및 [앱 관리를 계속하여](tenant-management-device-management.md) 장치 및 앱 관리를 배포합니다.
