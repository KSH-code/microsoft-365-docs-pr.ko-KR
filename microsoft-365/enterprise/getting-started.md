---
title: 시작하기 - 데스크톱 배포
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 데스크톱 배포 프로세스 소개
ms.openlocfilehash: a9ad328f6a2548a24a981ee3b49665c3091277c9
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112532"
---
# <a name="getting-started---desktop-deployment"></a>시작하기 - 데스크톱 배포

![](media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-2.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-1.png" alt="Getting Started" height="130" width="130" /></td>
<td><p><strong>시작하기: 사용자, 프로세스 및 기술 지침</strong></p>
<p>Windows 10 및 Office 365 ProPlus의 이점, 이전 배포와 비교하여 주요 변경 사항 및 고려 사항, Windows 10 및 Office 365 ProPlus로 원활하게 전환 할 수있는 모범 사례를 확인하세요.</p></td>
<td><a href="https://aka.ms/ddev0" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-13.png" alt="Getting Started" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>이 시리즈에서는 기존 도구를 사용하고 클라우드에서 사용할 수있는 새로운 기술, 서비스 및 방법을 소개하는 가장 좋은 방법을 설명합니다.  전체 데스크톱 배포 프로세스를 보려면 [데스크톱 배포 센터](https://aka.ms/HowToShift)를 방문하세요.
>

Windows 10 및 Office 365 ProPlus 로의 전환을 계획하고 실행하는 방법을 배우는 중심지인 데스크톱 배포 센터에 오신 것을 환영합니다. 이 곳에서 최신 생산성, 팀웍 및 공동 작업 환경을 통해 안전한 작업 공간을 활용할 수 있습니다.

새로운 데스크톱 환경을 한동안 배포하지 않았다면 배포 프로세스에 대한 많은 점이 개선되었다는 좋은 소식이 있습니다. 응용 프로그램 호환성과 같은 기존의 문제점은 오늘날에는 별로 문제가 되지 않습니다. 클라우드에서 제공하는 새로운 도구와 통찰력을 통해 이전보다 훨씬 빠르고 효율적으로 자신있게 업무를 진행할 수 있습니다.

이 소개 부분에서는 변경된 사항을 대략적으로 살펴보고, 데스크톱 배포 사이클을 간단히 알아봅니다. 여기서는 Windows 10 및 Office 365 ProPlus로 전환하기 위한 권장 단계를 안내하며 최신 관리 기술 및 접근 방식을 채택하면서 기존 도구와 프로세스를 활용하는 방법도 자세히 다룹니다.

## <a name="why-upgrade"></a>업그레이드가 필요한 이유

Windows 10과 Microsoft Intelligence Cloud를 함께 사용하면 사용자에게 가장 강력하고 안전한 작업 환경을 제공하는 동시에 지원 인프라를 단순화 할 수 있습니다.

최신 관리 방법의 주요 테넌트 중 하나는 항상 최신 상태를 유지하는 장치입니다. 이 시리즈를 통해 Windows 10 및 Office 365 ProPlus 로의 이전을 지원하기 위해 제공되는 새로운 기능과 반기별 릴리스를 통해 각각 최신 상태를 유지하는 방법에 대해 알아보세요.

[IT 전문가용 Windows 10](https://www.microsoft.com/itpro/windows-10)

[엔터프라이즈의 Office 365 ProPlus 정보](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)

## <a name="what-has-changed"></a>변경된 사항

먼저 마지막 데스크톱 배포 이후에 변경된 사항과 개선된 사항을 살펴보겠습니다. 얼마 동안 데스크톱 환경으로 전환하지 않은 경우 Windows 7과 Office 2010 또는 Office 2013을 사용하고 있을 것입니다. 이 경우 마지막 주요 업그레이드 이후에 몇 가지 사항이 개선되었다는 사실을 알게 될 것입니다. 일부 핵심 변경 내용은 다음과 같습니다.

**ID 및 액세스** : 클라우드 생산성, 보안 및 관리 서비스에 대한 연결성을 갖춘 Windows 10 및 Office 365 ProPlus는 새로운 ID 및 액세스 관리 서비스인 Azure AD (Azure Active Directory)가 핵심입니다. 이를 통해 클라우드 서비스 전체에 대한 단일 로그인 및 보안 연결이 가능하므로 Office 365, Intune 또는 Windows Autopilot과 같은 Microsoft 365 서비스를 활용하려면 Azure AD가 필요하게 됩니다.

[Microsoft 365](https://www.microsoft.com/microsoft-365/default.aspx)

**보안 사전 부팅 환경:** 64 비트 UEFI 펌웨어가 BIOS를 대체 합니다. 이것은 부팅 시간의 단축뿐만 아니라 Windows 10에서 많은 최신 보안 기능을 사용하기 위해 필요로 합니다. Windows 10은 BIOS에서도 실행되지만 UEFI를 강력히 추천드립니다. 아직 BIOS에서 UEFI로 전환하지 않고 64비트를 제대로 활용하지 않았다면, 지금이 적절한 시점입니다. Windows 10 업그레이드 도중 혹은 그 이후에 전환하는 데 도움이 되는 도구가 있습니다.

**클라우드 기반 장치 관리:** Microsoft Intune과 같은 서비스는 다른 모바일 장치를 관리하는 것 처럼 Windows 10 장치를 한 곳에서 관리하는 데 도움이 됩니다. Microsoft Intune을 특별하게 만들어 주는 것은 Microsoft Endpoint Configuration Manager로 Windows 10 장치를 공동 관리 할 수 있는 능력입니다. Configuration Manager를 사용하여 Windows 10으로 전환한 다음 Microsoft Intune을 추가할 수 있습니다. Microsoft Endpoint Configuration Manager를 함께 사용하면 Microsoft 지능형 클라우드에 연결된 조직 내에서 인텔리전트 에지가 됩니다. 이를 통해 조직의 인프라 또는 공개 클라우드 어디에 연결되어 있던지 장소에 구애받지 않고 사용자의 장치를 안전하게 관리 할 수 있습니다.

[Windows 10 장치의 공동 관리](https://docs.microsoft.com/configmgr/core/clients/manage/co-management-overview)

**클라우드 기반 배포 서비스:** 새로운 PC를 구입한 경우 Windows Autopilot 배포 서비스라고 하는 Microsoft 365 장치를 배포하는 데 도움이되는 새로운 클라우드 서비스를 도입하였습니다. Autopilot은 하드웨어 제공 업체와 통합되며 새로운 PC는 Autopilot에 자동으로 등록되어 새로운 PC가 최종 사용자에게 직접 배송됩니다. PC의 전원이 처음 켜지면 조직이 원하는 구성으로 빠르게 구성되고 사용자의 특정 요구에 맞게 사용자 정의됩니다.

[Windows Autopilot](https://www.microsoft.com/windowsforbusiness/windows-autopilot)

**Click-to-Run 배포:** Office 데스크톱 응용 프로그램을 구축할 때 Office 365 ProPlus가 선호되는 옵션입니다. 이것은 Office가 개발되면서 나오는 최신 혁신에 액세스할 수 있으므로 새로운 기능을 사용하기 위해 몇 년을 기다릴 필요가 없습니다. Click-to-Run 이라고하는 새 설치를 사용할 수도 있습니다.

Click-to-Run은 과거의 MSI 기반 패키지와는 많이 다릅니다. Click-to-run은 더 빠르고 가볍게 백그라운드에서 업데이트를 지원하여 사용자가 최신상태에서 작업하도록 합니다. 이것 또한 Office의 로컬 복사본이므로 Microsoft Endpoint Configuration Manager와 같은 기존 배포 도구를 계속 사용하여 응용 프로그램을 구축하고 구성할 수 있습니다.

[Office 365 ProPlus 배포 가이드](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus)

**반기별 업데이트:** Windows 10 및 Office 365 ProPlus로 이전하면 업데이트가 새로운 기능으로 반 년에 한 번 제공됩니다. 그러나 Microsoft가 클라우드에서 도움을 얻을 수 있는 통찰력을 제공함으로써 이러한 업데이트를 수백 또는 수천 개의 장치에 신속하고 정확하게 배포할 수 있습니다. 전체 업그레이드와 마찬가지로 기능 업데이트는 이전 릴리스의 응용 프로그램, 데이터 및 구성을 보존합니다.

## <a name="the-deployment-process-wheel"></a>배포 프로세스 사이클

시작하기 전에 높은 수준의 계획을 세우고 필요한 스폰서를 준비해야합니다. 이 배포 프로세스 사이클은 다음 배포 영역에서 관리할 핵심 팀 구성원 및 리소스를 식별하는 데 도움이 되는 중요한 단계를 설명합니다.

**[1 단계: 장치 및 앱 준비](https://aka.ms/mdd1) ** 성공적인 배포를 위해서는 먼저 무엇을 보유하고 있는 지 알아야합니다. 이는 기기와 앱 목록을 작성하고 호환성을 확인하는 과정을 의미합니다. 이를 돕기 위해 클라우드 기반 서비스인 Desktop Analytics에서 제공되는 도구를 활용할 수 있습니다. Desktop Analytics를 사용하면 수억 대의 PC에서 수집한 호환성 정보 및 진단 데이터를 활용하여 장치에서 실행되는 앱 및 드라이버를 평가할 수 있으므로 데스크톱 자산 준비 상태를 설정할 수 있습니다. 또한 Desktop Analytics에서 Configuration Manager로 "배포 준비가 된 PC" 목록을 내보낼 수 있으므로 대상 PC가 준비가 되는 대로 데이터 기반 컬렉션을 작성할 수 있습니다.

[업그레이드 준비 시작](https://docs.microsoft.com/windows/deployment/upgrade/upgrade-readiness-get-started)

**[2 단계: 디렉토리 및 네트워크 준비](https://aka.ms/mdd2) ** 2 단계 : 아직하지 않은 경우 ID 및 액세스 관리를 위해 Azure Active Directory를 구현해야 합니다. 또한 시스템 이미지, 응용 프로그램 패키지, 사용자 파일 및 업데이트를 이동하기 위해 네트워크를 준비해야합니다. 이는 많은 양의 추가 데이터를 의미합니다. 네트워크는 조직의 일상적인 작업에 영향을 미치지 않고 이 추가 로드를 처리 할 수 있는 용량이 있어야 합니다. 우리는 대역폭 조절 및 피어-투- 피어 옵션에서부터 동적 대역폭 제거 및 차등 업데이트에 이르는 다양한 네트워크 최적화 방법을 가지고 있습니다.

[BranchCache 및 피어 캐시](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**[3 단계: 사무실 및 업무용 응용 프로그램 제공](https://aka.ms/mdd3) ** Windows는 MSI 기반 설치를 여전히 계속 지원하지만 자동 배포 및 지속적인 업데이트에 최적화된 최신 설치 메커니즘 또한 지원합니다. Office 365 ProPlus 및 Office 2019 클라이언트는 Click-to-Run 설치 기술을 사용합니다. 다양한 UWP 응용 프로그램을 사용할 수 있게 하려는 경우 또한 새로운 MSIX 기반 패키징 응용 프로그램을 사용하는 타사 응용 프로그램 및 사내 개발 된 기간 업무 (LOB) 응용 프로그램을 배포하는 경우가 늘고 있습니다. 이 단계는 앱이 자동화된 배포를 준비 할 수 있도록 하며, Click-to-Run, MSIX, 전통적 MSI 기반 앱을 사용하여 앱을 배포하는지 또는 설정한 비즈니스의 Microsoft 스토어에서 배포한 UWP 앱인지에 상관없이 성공적으로 배포되도록 설정합니다.

[MSIX 소개](https://blogs.msdn.microsoft.com/sgern/2018/06/15/msix-intro/)

**[4 단계 : 사용자 파일 및 설정 마이그레이션](https://aka.ms/mdd4)** 이는 PC 교체 또는 업그레이드 주기에서 중요한 단계입니다. 사용자의 파일, 데이터 및 설정이 성공적으로 이전되고 마이그레이션 중에 보존되도록 해야 합니다. 이 단계에서는 잘 알려진 옵션 및 새 옵션을 포함하여 수동 또는 자동 마이그레이션에 사용할 수있는 옵션을 설명합니다.

이전 업그레이드에서와 마찬가지로 사용자 상태 마이그레이션 도구는 이 프로세스를 자동화하는 유용한 도구로 계속 사용되며 Microsoft Endpoint Configuration Manager 또는 Microsoft Deployment Toolkit을 사용하여 조정된 마이그레이션의 중요한 부분으로 남아 있습니다. 그러나 마이그레이션시 이 모든 데이터를 이동하는 것은 PC 당 수백 기가바이트를 두 번 전송 (기존 데스크톱에서 한 번, 새로운 데스크톱에서 다시 한 번)할 때 물리적으로 PC 교체의 타이밍 병목 현상이 될 수 있습니다. OneDrive에서 사용할 수 있는 새로운 옵션은 사용자 문서, 사진 및 용량이 큰 데스크톱 파일을 클라우드 상에서 배포에 앞서 동기화하는 데 사용되는 [알려진 폴더 이동]입니다.

[알려진 Windows 폴더를 OneDrive로 리디렉션 및 이동](https://docs.microsoft.com/onedrive/redirect-known-folders)

**[5단계: 보안 및 규정 준수](https://aka.ms/mdd5)** 보안 및 규정 준수는 Windows 10 및 Office 365 ProPlus로 전환할 때 비교적 크게 무리 없이 진행되는 영역입니다. 사용자는 새로운 기본 제공 기능을 숙지하고, 이미 사용 중인 기능과 비교하는 것이 중요합니다. 예를 들어 가상화 기반 보안을 사용하는 Windows 10의 새로운 기능은 핵심 프로세스 및 비밀을 운영 체제와 격리하여 자격 증명 도난을 방지하고, 브라우저 기반 악용 및 악성 코드로부터 보호할 수 있습니다. 또한 Advanced Threat Protection과 같은 클라우드 서비스는 보안 강화, 사후 위반 감지, 조사 및 대응을 위한 통합 플랫폼을 제공합니다. 그뿐 아니라 Advanced Threat Protection은 악의적인 전자 메일 첨부 파일, 안전하지 않은 하이퍼링크 등으로부터 사용자를 보호할 수 있습니다.

[Microsoft 보안](https://www.microsoft.com/security/default.aspx)

**[6단계: OS 배포 및 기능 업데이트](https://aka.ms/mdd6)** 모든 준비가 완료되면 다음 단계로, OS 이미지를 배포합니다. System Center Configuration Manage 작업 시퀀스와 인프라를 사용하면 과도한 전환이 수행될 수 있습니다. 따라서 권장되는 방식은 대표적인 하드웨어 및 앱 집합을 사용하여 조직의 “얼리 어답터 그룹”을 대상으로 단계별 배포를 진행하는 것입니다. 그런 후 해당 장치 및 사용자의 데이터를 토대로 점점 더 많은 PC를 타기팅할 수 있습니다.

[Configuration Manager의 운영 체제 배포 소개](https://docs.microsoft.com/configmgr/osd/understand/introduction-to-operating-system-deployment)

**[7 단계 : 서비스로서의 Windows 및 Office](https://aka.ms/mdd7) ** 이것은 사용자의 데스크톱 점유 공간을 유지 관리하는 방식에서 큰 변화를 나타냅니다. Windows 10 및 Office 365 ProPlus로 전환하면 서비스로서의 Windows 및 Office 관리로 이동할 수 있습니다. 몇 해에 한 번씩 엄청난 기술 변화가 일어나는 대신에 새로운 기능, 경험 및 보호 기능을 사용자에게 지속적으로 제공 할 것입니다. 반기별 기능 업데이트는 매년 가을 및 봄에 새로운 기능을 제공하며, 월간 누적 품질 업데이트에는 보안, 안정성 및 버그 수정이 포함됩니다. Office 2019 클라이언트를 배포 할 수도 있지만 Office 365 ProPlus로 이동하는 것을 추천드립니다. 이것은 Windows와 유사한 서비스 계획을 따르므로 사용자는 Office 응용 프로그램에 대한 업데이트를 정기적으로 받습니다.

![](media/getting-started-media/getting-started-media-2.png)

[서비스로서의 Windows 개요](https://docs.microsoft.com/windows/deployment/update/waas-overview)
[서비스로서의 Office 개요](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

**[8 단계 : 사용자 커뮤니케이션 및 교육](https://aka.ms/mdd8) ** 이 마지막 단계는 팀워크, 커뮤니케이션, 보안 등을 향상시키는 새로운 기능의 사용을 유도하는 중요한 단계입니다. 초기도입자 링 외부의 사용자를 대상으로 광범위한 배포를 수행하기 전에 사용자 커뮤니케이션 및 교육을 시작하는 것이 좋습니다. 이를 통해 사람들이 Office, Windows 또는 기타 업무용 응용 프로그램 및 서비스에서 새로운 기능을 사용하는 방법에 대한 변경을 원하도록 유도하는 데 도움이 됩니다. 이것의 지원을 위해 Microsoft FastTrack을 통해 무료 온라인 교육을 제공합니다. 또한 무료 샘플 커뮤니케이션 계획 및 일정을 이메일, 소셜 및 인트라넷 템플릿에 함께 게시하여 Windows 10의 롤아웃을 지원합니다. Microsoft 365 또는 Office 365 조직인 경우 직접 지원의 대상이 될 수도 있습니다.

## <a name="next-step"></a>다음 단계

이제 Windows 10 및 Office 365 ProPlus의 새로운 기능과 차이점을 확인하고 권장되는 배포 프로세스 휠을 살펴 보았습니다. Windows 10 및 Office 365 ProPlus로 전환할 수있는 조단구에 대한 이러한 경험을 바탕으로 시작해 보겠습니다.

## <a name="step-1-device-and-app-readinesshttpsakamsmdd1"></a>[1단계: 장치 및 앱 준비](https://aka.ms/mdd1)

