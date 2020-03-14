---
title: Microsoft 365 Enterprise로 마이그레이션
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 조직 전체에서 Microsoft Office, Office 서버 및 Windows 버전을 Microsoft 365 Enterprise로 마이그레이션하는 프로세스를 단계별로 안내합니다.
ms.openlocfilehash: 06cacbb45a98bb62f53866b0d2ab7ba393e609a0
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633246"
---
# <a name="migration-to-microsoft-365-enterprise"></a>Microsoft 365 Enterprise로 마이그레이션

대부분의 엔터프라이즈 조직은 여러 릴리스의 운영 체제, 클라이언트 소프트웨어 및 서버 소프트웨어가 섞여 있는 이기종 환경을 사용하고 있습니다. Microsoft 365 Enterprise에는 클라우드 기술을 활용하도록 고안된 생산성 기능과 이러한 IT 인프라의 가장 안전한 핵심 구성 요소 버전이 포함되어 있습니다.

Microsoft 365 Enterprise 통합 제품군의 비즈니스 가치를 최대화하려면 다음 릴리스를 마이그레이션하기 위한 계획을 세우고 전략을 구현하세요.

- 컴퓨터에 설치된 Office 클라이언트를 Office 365 ProPlus로
- 서버에 설치된 Office 서버를 Office 365의 해당 서비스로
- 장치의 Windows 7 및 Windows 8.1을 Windows 10 Enterprise로

>[!Note]
>Windows 7은 **2020년 1월 14일**에 지원이 종료됩니다. 자세한 내용은 [여기](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)를 클릭하세요.
>

시간이 지나면서 조직에서 이러한 모든 마이그레이션을 완료하게 되면 Microsoft 365 Enterprise를 통해 조직의 팀워크와 창의성이 극대화되는 보안 통합형 [최신 작업 환경](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)에 더 가까워지게 됩니다. 

특정 Office 365 워크로드에 대한 사용자 및 데이터 마이그레이션에 대한 자세한 내용은 다음을 참조합니다.

- Exchange Server에서 Exchange Online으로 마이그레이션하는 사용자 메일함은 [Exchange Online 워크로드](exchangeonline-workload.md)를 참조하세요.
- SharePoint Server에서 SharePoint Online으로 마이그레이션하는 SharePoint 데이터는 [SharePoint Online 워크로드](sharepoint-online-onedrive-workload.md)를 참조하세요.
- 비즈니스용 Skype Online을 Microsoft Teams으로 마이그레이션시 [Microsoft Teams 워크로드](teams-workload.md)를 참조하세요.

## <a name="migration-for-microsoft-office-client-products"></a>Microsoft Office 클라이언트 제품에 대한 마이그레이션

많은 대기업 및 중소기업에서는 Word, Excel 및 PowerPoint와 같은 이전 버전의 Office 클라이언트 제품 버전을 조합해서 사용하고 있을 것입니다. 이러한 이전 버전은 다음과 같을 수 있습니다.

- 최신 보안 업데이트 및 지원 수정 프로그램으로 [업데이트](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)할 수 있지만 경우에 따라 이 프로세스가 수동으로 수행되며 조직 전체 규모로 진행되지 않을 수도 있습니다.
- Microsoft의 클라우드 기술을 활용하여 비즈니스의 디지털 혁신을 이룰 수 있도록 최적화되지 않았습니다.
- 새로운 기능이 포함되어 있지 않습니다.
 
Microsoft 365 Enterprise에는 Microsoft 365 Enterprise 라이선스로 사용할 수 있고 Microsoft 클라우드에서 설치 및 업데이트되는 Office 클라이언트 제품 버전인 Office 365 ProPlus가 포함되어 있습니다.  Office 365 ProPlus에는 보안 업데이트와 최신 기능이 포함되어 있습니다. 자세한 내용은 [엔터프라이즈의 Office 365 ProPlus](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)를 참조하세요.

### <a name="office-2007"></a>Office 2007

Office 2007 릴리스에 포함된 Office 버전의 경우 지원 종료 기간이 이미 지났습니다. 자세한 내용은 [Office 2007 지원 종료 로드맵](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap)을 참조하세요.

Office 2007을 실행하는 컴퓨터를 Office 2010, Office 2013 또는 Office 2016으로 업그레이드하는 대신, 다음을 수행하는 것이 좋습니다.

1. 사용자를 위한 Microsoft 365 라이선스 획득 및 할당
2. 컴퓨터에서 Office 2007 제거
3. 개별적으로 또는 IT 롤아웃 작업과 함께 Office 365 ProPlus 설치. 자세한 내용은 [4단계: Office 365 ProPlus](office365proplus-infrastructure.md)를 참조하세요.

Office 365 ProPlus는 업데이트를 자동으로 설치하고 Office 365의 클라우드 기반 서비스를 활용하여 향상된 보안 및 생산성을 누릴 수 있습니다.

### <a name="office-2010"></a>Office 2010

Office 2010 릴리스에 있는 Office 버전의 경우에는 **2020년 10월 13일**에 지원이 종료됩니다. 자세한 내용은 [Office 2010 지원 종료 로드맵](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)을 참조하세요.

Office 2010을 실행하는 컴퓨터를 Office 2013 또는 Office 2016으로 업그레이드하는 대신(둘 다 수동으로 업데이트해야 함), 다음을 수행하는 것이 좋습니다. 

1. 사용자를 위한 Microsoft 365 라이선스 획득 및 할당
2. 컴퓨터에서 Office 2010 제거
3. 개별적으로 또는 IT 롤아웃 작업과 함께 Office 365 ProPlus 설치. 자세한 내용은 [4단계: Office 365 ProPlus](office365proplus-infrastructure.md)를 참조하세요.

Office 365 ProPlus는 보안 및 새로운 기능 업데이트를 자동으로 설치하고 Microsoft 365의 클라우드 기반 서비스를 활용하여 향상된 보안 및 생산성을 누릴 수 있습니다.

### <a name="office-2013-and-office-2016"></a>Office 2013 및 Office 2016

Office 2013 및 Office 2016 버전의 Office에 대한 지원 로드맵의 종료는 아직 확인되지 않았습니다. 그러나 Office 2010과 같이 [보안 업데이트를 설치](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)해야 합니다. 이는 조직 규모에 따라 적절히 확장이 되지 않을 수 있습니다.

Office 2013 또는 Office 2016용 최신 보안 업데이트로 컴퓨터를 계속 업데이트하거나 Office 2013에서 Office 2016로 컴퓨터를 업데이트하는 대신 다음 사항을 고려해 보세요.

1. 사용자를 위한 Microsoft 365 라이선스 획득 및 할당
2. 컴퓨터에서 Office 2013 또는 Office 2016을 제거합니다.
3. 개별적으로 또는 IT 롤아웃 작업과 함께 Office 365 ProPlus 설치. 자세한 내용은 [4단계: Office 365 ProPlus](office365proplus-infrastructure.md)를 참조하세요.

Office 365 ProPlus는 보안 및 새로운 기능 업데이트를 자동으로 설치하고 Microsoft 365의 클라우드 기반 서비스를 활용하여 향상된 보안 및 생산성을 누릴 수 있습니다.

## <a name="migration-for-microsoft-office-server-products"></a>Microsoft Office 서버 제품에 대한 마이그레이션

많은 대기업 및 중소기업에서는 Exchange Server 및 SharePoint Server와 같은 이전 버전의 Office Server 제품 버전을 조합해서 사용하고 있을 것입니다. 이러한 이전 버전은 다음과 같을 것입니다.

- 최신 보안 업데이트 및 지원 수정 프로그램으로 업데이트하는 것이 좋습니다. 경우에 따라 이러한 업데이트는 매월 출시됩니다.
- Microsoft의 클라우드 기술을 활용하여 비즈니스의 디지털 혁신을 이룰 수 있도록 최적화되지 않았습니다.
- Microsoft Teams와 같은 새로운 생산성 응용 프로그램이 포함되어 있지 않습니다.
- Exchange Advanced Threat Protection과 같은 최신 보안 기능이 포함되어 있지 않습니다.

Microsoft 365 Enterprise에는 웹 브라우저 및 Outlook 클라이언트와 같은 온-프레미스 버전의 Office 서버 소프트웨어와 동일한 도구 중 일부를 사용하는 클라우드 기반 Office server 서비스 버전을 포함하는 Office 365이 포함되어 있습니다.  이러한 서비스는 IT 부서가 연관되지 않고도 보안을 위해 지속적으로 업데이트되므로 온-프레미스 서버를 유지 관리하고 업데이트하는 데 걸리는 시간이 절약됩니다. 이러한 서비스에는 Office 서버 소프트웨어에 없는 새로운 기능 향상 기능도 있습니다. 

### <a name="office-server-2007"></a>Office Server 2007

Office 2007 릴리스에 포함된 서버 제품의 경우 지원 종료 기한이 이미 경과되었습니다. 자세한 내용은 다음 문서를 참조하세요.

- [Exchange 2007 지원 종료 로드맵](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [SharePoint Server 2007 지원 종료 로드맵](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [Project Server 2007 지원 종료 로드맵](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [Office Communications Server 지원 종료 로드맵](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [PerformancePoint Server 2007 지원 종료 로드맵](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

Office 2007 릴리스의 서버 제품을 Office 2010, Office 2013 또는 Office 2016 릴리스의 서버 제품으로 업그레이드하는 대신, 다음을 수행하는 것이 좋습니다.

1. Office 2007 서버의 데이터를 Office 365로 마이그레이션. 이를 지원하기 위해 Microsoft 파트너를 고용합니다.
2. 사용자에게 새 기능 및 작업 프로세스 롤아웃
3. Office 2007 서버 제품을 실행하는 온-프레미스 서버가 더 이상 필요하지 않은 경우 서비스 해제

### <a name="office-server-2010"></a>Office Server 2010

Office 2010 릴리스 서버 제품의 경우 다음에 대한 지원 종료는 **2020년 10월 13일**입니다.

- [Exchange Server 2010](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support)
- [SharePoint Server 2010](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010)

Office 2010 릴리스의 서버 제품을 Office 2013 또는 Office 2016 릴리스의 서버 제품으로 업그레이드하는 대신, 다음을 수행하는 것이 좋습니다.

1. Office 2010 서버의 데이터 Microsoft 365로 마이그레이션 이에 대한 도움이 필요하면 [Microsoft 365의 FastTrack](https://fasttrack.microsoft.com/microsoft365) 또는 Microsoft 파트너 고용을 참조하세요.
2. 사용자에게 새 기능 및 작업 프로세스 롤아웃
3. Office 2010 서버 제품을 실행하는 온-프레미스 서버가 더 이상 필요하지 않은 경우 서비스 해제

### <a name="office-server-2013"></a>Office Server 2013

Office 2013 릴리스 서버 제품의 경우, 지원 종료가 결정되지 않았습니다. Office 2013 릴리스의 서버 제품을 Office 2016 릴리스의 서버 제품으로 업그레이드하는 대신, 다음을 수행하는 것이 좋습니다.

1. Office 2013 서버의 데이터를 Office 365로 마이그레이션. 이를 지원하기 위해 [Microsoft 365에 대한 FastTrack](https://fasttrack.microsoft.com/microsoft365)을 참조하거나 Microsoft 파트너를 고용하세요.
2. 사용자에게 새 기능 및 작업 프로세스 롤아웃
3. Office 2013 서버 제품을 실행하는 온-프레미스 서버가 더 이상 필요하지 않은 경우 서비스 해제

### <a name="office-server-2016"></a>Office Server 2016

Office 2016 릴리스 서버 제품의 경우, 지원 종료가 결정되지 않았습니다. 클라우드 기반 서비스 및 개선 기능을 활용하여 비즈니스의 디지털 혁신을 진행하려면 다음을 수행하는 것이 좋습니다.

1. Office 2016 서버의 데이터를 Office 365로 마이그레이션. 이를 지원하기 위해 [Microsoft 365에 대한 FastTrack](https://fasttrack.microsoft.com/microsoft365)을 참조하거나 Microsoft 파트너를 고용하세요.
2. 사용자에게 새 기능 및 작업 프로세스 롤아웃
3. Office 2016 서버 제품을 실행하는 온-프레미스 서버가 더 이상 필요하지 않은 경우 서비스 해제

## <a name="migration-for-microsoft-windows-7-and-81"></a>Microsoft Windows 7 및 8.1에 대한 마이그레이션

Windows 7은 **2020년 1월 14일**에 지원이 종료됩니다. Windows 7 또는 Windows 8.1이 실행 중인 장치를 마이그레이션하려면 [현재 위치 업그레이드](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade)를 수행할 수 있습니다. 

추가 방법에 대해서는 [Windows 10 배포 시나리오](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)를 참조하세요. 직접 [Windows 10 배포를 계획](https://aka.ms/planforwin10deployment)할 수도 있습니다.

## <a name="summary-of-options-for-office-2010-clients-and-servers-and-windows-7"></a>Office 2010 클라이언트 및 서버와 Windows 7에 대한 옵션 요약

이러한 제품에 대한 업그레이드, 클라우드로 이동 옵션을 알기 쉽게 요약한 내용을 보려면 [지원 종료 포스터](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)를 참조하세요.

[![Office 2010 클라이언트 및 서버와 Windows 7에 대한 지원 종료 포스터 이미지](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)

Microsoft 365 Enterprise에서 기본적으로 사용되는 경로와 결과 목적지 지원이 강조된 이 한 페이지짜리 포스터를 사용하여 Office 2010 클라이언트 및 서버 제품과 Windows 7의 지원 종료를 방지하는 다양한 방법을 빠르게 파악합니다.

[이 포스터를 다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)하고 편지형, 법률형 또는 타블로이드(11 x 17) 형식으로 인쇄할 수 있습니다.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법

다음 리소스를 사용하여 Microsoft의 IT 전문가가 회사를 Microsoft 365 Enterprise로 마이그레이션한 방법을 알아보세요. 

- [Microsoft Office 365 ProPlus 배포 및 업데이트](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Microsoft에서 150,000개의 사서함을 Exchange Online으로 마이그레이션](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [SharePoint를 클라우드로: Microsoft가 자체 마이그레이션을 수행한 방법 알아보기](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [Microsoft의 Windows 10dmf 현재 위치 업그레이드 방식으로 배포](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Windows 10 배포: Microsoft IT의 팀과 트릭](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)(비디오)

## <a name="transition-your-entire-organization"></a>전체 조직 전환

전체 조직을 Microsoft 365 Enterprise의 제품 및 서비스로 전환하는 방법을 더 잘 이해하려면 [전환 포스터](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)를 다운로드하세요.

[![Microsoft 365로 전환 포스터 이미지](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)

이 두 페이지 포스터는 신속하게 기존 인프라를 인벤터리하여 Microsoft 365 Enterprise에서 해당 제품이나 서비스로 전환하는 방법에 대한 지침을 제공합니다. 여기에는 Windows와 Office 제품, 장치 관리, ID, 정보 및 위협 방지와 같은 기타 인프라 및 보안 요소가 포함됩니다.

[이 포스터를 다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)하고 편지형, 법률형 또는 타블로이드(11 x 17) 형식으로 인쇄할 수 있습니다.

## <a name="result"></a>결과

조직에 있는 이전 버전의 Microsoft Office, Office 서버 및 Windows가 Microsoft 365 Enterprise 버전으로 마이그레이션되었습니다.
