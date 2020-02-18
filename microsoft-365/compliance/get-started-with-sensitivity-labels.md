---
title: 민감도 레이블 시작
f1.keywords:
- CSH
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
description: 조직의 데이터를 보호하는 데 도움이 되는 민감도 레이블 구현을 시작할 준비가 되었지만 어디서부터 시작해야 할지 모르겠나요? 레이블 여행에 도움이 되는 몇 가지 실용적인 지침을 읽으세요.
ms.openlocfilehash: efb0d8401cca8fd0e8c2450a5d35788015f37dad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073183"
---
# <a name="get-started-with-sensitivity-labels"></a>민감도 레이블 시작

민감도 레이블이 무엇인지와 조직의 데이터를 보호하는 데 도움이 되는 방법에 대한 자세한 내용은 [민감도 레이블에 대한 자세한 정보](sensitivity-labels.md)를 참조하세요.

[Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)을 사용하는 경우 레이블을 통합 레이블 플랫폼으로 마이그레이션해야 하는지 여부와 사용할 클라이언트 레이블 클라이언트를 결정합니다.
- [내 테넌트가 통합 레이블 플랫폼에 있는지 어떻게 확인할 수 있나요?](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [Windows 컴퓨터에 사용할 레이블 클라이언트 선택](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

민감도 레이블을 사용하여 조직의 데이터를 보호하기 시작할 준비가 되면 다음을 수행합니다.

1. **레이블을 만듭니다.** 다양한 민감도 수준의 컨텐츠에 대한 조직의 분류체계에 따라 민감도 레이블을 작성하고 이름을 지정하십시오. 사용자가 이해할 수 있는 일반적인 이름이나 용어를 사용합니다. 분류 체계가 아직 설정되지 않은 경우 개인, 공개, 일반, 기밀 및 극비와 같은 문구로 레이블 이름으로 시작하는 것이 좋습니다. 그런 다음 하위 레이블을 사용하여 범주별로 비슷한 레이블을 그룹화할 수 있습니다. 레이블을 만들 때 도구 설명 텍스트를 사용하여 사용자가 적절한 레이블을 선택하는 데 도움을 줄 수 있습니다.

2. **각 레이블이 수행할 수 있는 작업을 정의합니다.** 각 레이블과 연결할 보호 설정을 구성합니다. 예를 들어 민감도가 낮은 콘텐츠(예: "일반"레이블)에 머리글이나 바닥글만 적용하고 민감도가 높은 콘텐츠(예: "기밀" 레이블)에는 워터마크, 암호화 및 엔드포인트 보호 기능을 적용하고자 할 수 있습니다.

3. **레이블을 게시합니다.** 민감도 레이블이 구성되 면 레이블 정책을 사용하 여 해당 레이블을 게시합니다. 어떤 사용자와 그룹에 레이블과 정책 설정을 사용할지 결정합니다. 단일 레이블은 다시 사용할 수 있습니다. 한번 정의한 후 다양한 사용자에게 할당된 여러 레이블 정책에 이를 포함시킬 수 있습니다. 예를 들어, 소수의 사용자 에게만 레이블 정책을 할당하여 민감도 레이블을 파일럿 할 수 있습니다. 그런 다음 조직 전체에 레이블을 롤아웃할 준비가되면 레이블에 대한 새 레이블 정책을 작성하고 이번에는 모든 사용자를 지정하십시오.

관리자, 사용자 및 Office 앱과 서비스가 민감도 레이블 사용을 위해 수행하는 작업의 기본 흐름:

![민감도 레이블의 워크플로를 보여 주는 다이어그램](../media/Sensitivity-label-flow.png)

## <a name="common-scenarios-for-sensitivity-labels"></a>민감도 레이블에 대한 일반적인 시나리오

다음 문서를 사용하여 민감도 레이블 배포를 지원합니다.

|필요|설명서|
|----------------|---------------|
|조직의 데이터를 보호하는 데 도움이 되는 민감도 레이블을 만들고 게시합니다.|[민감도 레이블과 해당 정책 생성 및 구성](create-sensitivity-labels.md)|
|민감도 레이블로 문서 및 전자 메일을 암호화하고 액세스할 수 있는 사람과 해당 컨텐츠를 사용하는 방법을 제한합니다. |[민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠 액세스 제한](encryption-sensitivity-labels.md)|
|암호화 레이블이 지정된 문서에 대해 SharePoint(및 OneDrive)의 공동 작업 기능을 사용하도록 설정합니다. | [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용(공개 미리 보기)](sensitivity-labels-sharepoint-onedrive-files.md)
|콘텐츠가 만들어 질 때 레이블이 지정되도록 Office 앱의 민감도 레이블을 관리합니다. |[Office 앱의 민감도 레이블 사용](sensitivity-labels-office-apps.md)|
|콘텐츠를 만들 때 자동으로 민감도 레이블 적용하거나 사용자에게 레이블을 추천합니다. | [민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md)|
|민감도 레이블을 사용하여 Teams와 SharePoint에서 콘텐츠 보호 |[Microsoft Teams, Office 365 그룹 및 SharePoint 사이트(공개 미리 보기)에서 민감도 레이블 사용](sensitivity-labels-teams-groups-sites.md)|
|온-프레미스 데이터 저장소에 저장된 파일을 검색하고, 레이블을 지정하고, 보호합니다. |[파일을 자동으로 분류하고 보호하는 Azure Information Protection 스캐너 배포](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|클라우드 데이터 저장소에 저장된 파일을 검색하고, 레이블을 지정하고, 보호합니다. |[클라우드에 저장된 데이터를 검색하고, 분류하고, 레이블을 지정하고, 보호](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|배포 상태 보고를 위해 민감도 레이블을 사용하고 레이블 구성을 미세 조정하는 방법을 보여줍니다.|[레이블 분석을 통한 레이블 사용량 보기](label-analytics.md)|


## <a name="end-user-documentation-for-sensitivity-labels"></a>민감도 레이블용 최종 사용자 설명서

- [Office에서 파일 및 전자 메일에 민감도 레이블 적용](https://support.office.com/article/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Office의 민감도 레이블과 관련된 알려진 문제점](https://support.office.com/en-us/article/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Office에서 파일 및 전자 메일에 자동으로 민감도 레이블 적용 또는 추천](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)

- [민감도 레이블 자동 적용 또는 추천에 대한 알려진 문제](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)


