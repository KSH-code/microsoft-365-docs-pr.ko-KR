---
title: Contoso Corporation의 최상위 프로젝트를 위한 격리된 팀
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: '요약: Contoso가 비밀 프로젝트의 보안이 강화된 팀을 사용하여 새 제품 및 서비스 제품군을 개발하는 방법'
ms.openlocfilehash: b8794502afcb77a8e597a1b05dfc92acd093f23a
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656072"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Contoso Corporation의 최상위 프로젝트를 위한 격리된 팀

임원진의 오프사이트 이후 Contoso의 CEO는 이후 5년 동안 Contoso의 이익을 두 배로 증가할 수 있는 새로운 제품군의 개발을 주문했습니다. 비즈니스, 엔지니어링 및 시장 계획을 개발하는 최상위 프로젝트의 이름이 **Project 2X로** 지정되고 회사의 주요 직원도 채용했습니다. 

연구 및 개발의 일정이 긴밀하게 유지된 것이기 때문에 공동 작업의 효율성을 보장하고 모임, 지속적인 대화 및 파일 저장소를 제공해야 합니다.

Project 2X의 결과물은 비즈니스 계획, 제품 및 엔지니어링 사양, 마케팅 자료 및 일정(Word, Excel 및 PowerPoint 파일 형식)입니다. 

중요한 특성으로 인해 이러한 파일에 대한 액세스는 다음이 있습니다.

- Project 2X 팀 구성원 및 선임 리더로 제한됩니다.
- 파일이 보안 폴더 외부에 배포된 경우에도 Project 2X 팀 구성원 및 고위 임원만 액세스할 수 있도록 권한이 암호화되고 보호됩니다.

Contoso IT 직원은 Project 2X에 대한 보안이 있는 팀과 이러한 단계를 사용했습니다. [](secure-teams-security-isolation.md)

## <a name="step-1-created-a-private-team"></a>1단계: 비공개 팀 생성

먼저, 팀의 기본 SharePoint 사이트에 대한 액세스를 보호하기 위해 Contoso IT 관리자가 [권장되는 SharePoint 액세스 정책을 구성했습니다.](../security/office-365-security/sharepoint-file-access-policies.md)

다음으로 Contoso IT 관리자가 Project 2X라는 새 비공개 팀을 만들어 Project 2X 직원의 사용자 계정을 구성원으로 추가했습니다. 또한 Project 2X 팀 소유자만 비공개 채널을 만들 수 있도록 팀을 구성했습니다.

구성 세부 정보는 비공개 팀 [만들기를 참조합니다.](secure-teams-security-isolation.md#create-a-private-team)

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>2단계: Project 2X 팀에 대한 민감도 레이블 생성

Contoso 관리자는 **Project 2X라는** 새 민감도 레이블을 만들었다.

- 암호화를 사용하도록 설정했습니다.
- Project Co-Author 2X Microsoft 365 그룹에 대한 사용 권한이 허용됩니다.
- 선임 리더십 그룹에 대한 보기 권한 허용
- 관리되지 않는 장치에 대한 액세스가 차단되었습니다.

다음을 **통해** 기본적으로 Project 2X SharePoint 사이트의 문서 섹션에 있는 파일이 보호됩니다.

- Project 2X Microsoft 365 그룹의 구성원에게만 모든 권한을 허용하고 선임 리더십 그룹에 대한 읽기 권한만 허용하는 사이트 권한
- 사이트에서 이동하거나 복사하는 경우 파일과 함께 이동하는 암호화 및 사용 권한이 있는 Project 2X 민감도 레이블입니다.

구성 세부 정보는 민감도 레이블 [만들기를 참조합니다.](secure-teams-security-isolation.md#create-a-sensitivity-label)

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>3단계: 기본 SharePoint 사이트 구성

먼저, 팀의 기본 SharePoint 사이트에 대한 액세스를 보호하기 위해 Contoso IT 관리자가 [권장되는 SharePoint 액세스 정책을 구성했습니다.](../security/office-365-security/sharepoint-file-access-policies.md)

그런 다음 사이트에 대한 추가 사용 권한 설정을 구성했습니다.

- Project 2X 그룹 구성원이 사이트에 대한 액세스를 공유하지 못하게 합니다. 구성 세부 정보는 보안이 강화된 팀에 대한 [SharePoint 설정을 참조하세요.](secure-teams-security-isolation.md#sharepoint-settings)
- 선임 리더십 그룹의 읽기 권한

그런 다음 Project 2X 그룹 구성원이 사이트에 대한 액세스를 공유하지 못하도록 사이트에 대한 추가 사용 권한 설정을 구성했습니다. 

Project 2X에 대한 비공개 채널을 만들 때 그룹 소유자는 게스트 공유를 사용하지 않도록 설정하고 기본 공유 링크를 **특정** 사용자 값으로 설정했습니다.

다음은 보안이 고지된 Project 2X 팀의 구성 결과입니다.

![Project 2X 팀의 결과 구성](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>4단계: Project 2X 팀 구성원 교육

Contoso 보안 직원은 다음을 단계적으로 진행하는 필수 과정으로 Project 2X 팀 구성원을 교육했습니다.

- 새 Project 2X 팀에 액세스하고, 모임 및 채팅을 사용하는 방법 및 팀 파일에서 공동 작업하는 방법
- 팀에서 새 파일을 만들고 로컬로 만든 새 파일을 업로드하는 방법
- Project 2X 민감도 레이블로 파일에 레이블을 지정하는 방법
- Project 2X 레이블이 팀을 떠나도 파일을 보호하는 방법에 대한 데모입니다.

결과적으로 Project 2X 팀 구성원이 채팅, 모임 및 파일을 위한 안전한 환경에서 공동 작업을 하는 안전한 환경이 이되었습니다.

다음은 Project 2X 민감도 레이블이 할당된 프로젝트 2X 사이트에 저장된 파일의 예입니다.

![밑에 있는 Project 2X 사이트에 저장된 파일의 예](../media/contoso-team-for-top-secret-project-example.png)

몇 가지 경우에 Project 2X 팀 구성원은 오프라인 작업을 위해 Project 2X 레이블로 보호된 파일을 로컬 드라이브에 다운로드했습니다. 

그러나 자격 증명을 열 때 자격 증명을 입력하라는 메시지가 표시되면 실수를 실현하고 삭제했습니다.

Teams의 공동 작업 환경과 Microsoft 365의 보안 기능 때문에 Project 2X의 세부 정보는 프로젝트 기간 동안 비밀로 유지되었습니다. Contoso는 계획을 발표하고 고객 및 투자가의 즐거움과 경쟁 업체를 위해 새로운 제품 및 서비스를 출시하는 중입니다.

## <a name="next-step"></a>다음 단계

[조직에 보안이 고지된](secure-teams-security-isolation.md) 팀을 배포합니다.

