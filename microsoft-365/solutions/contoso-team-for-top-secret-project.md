---
title: Contoso Corporation의 최상위 프로젝트를 위한 격리된 팀
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: '요약: Contoso가 비밀 프로젝트를 위해 보안이 강화된 팀을 사용하여 새 제품 및 서비스 제품군을 개발하는 방법을 설명하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: c789e74bc54183f16f7de7801ecc77b76f4913f6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191280"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Contoso Corporation의 최상위 프로젝트를 위한 격리된 팀

임원진 오프사이트 이후, Contoso의 CEO는 다음 5년 동안 Contoso의 이익을 두 배로 증가할 수 있는 새로운 제품군의 제품 및 서비스 개발을 주문했습니다. 비즈니스, 엔지니어링 및 시장 계획을 개발하기 위한 최고의 비밀 프로젝트는 Project **2X로** 이름이 지정되고 회사 전체의 주요 직원을 모집했습니다. 

연구 및 개발 일정이 협조적이기 때문에 공동 작업을 효율적으로 진행하고 안전한 모임, 지속적인 대화 및 파일 저장소를 제공해야 합니다.

이러한 결과로 Project 2X의 결과물은 Word, Excel 및 PowerPoint 파일 형식의 비즈니스 계획, 제품 및 엔지니어링 사양, 마케팅 자료 및 일정입니다. 

중요한 특성으로 인해 이러한 파일에 대한 액세스는 다음이 있습니다.

- 2X Project 수석 리더십으로 제한됩니다.
- 파일이 보안 폴더 외부에 배포된 경우에도 2X 팀 Project 고위 임원만 액세스할 수 있도록 권한이 암호화되고 보호됩니다.

Contoso IT 직원은 2X 및 Project 보안이 있는 팀을 사용했습니다. [](secure-teams-security-isolation.md)

## <a name="step-1-created-a-private-team"></a>1단계: 비공개 팀 생성

먼저, 팀의 기본 SharePoint 사이트에 대한 액세스를 보호하기 위해 Contoso IT 관리자는 권장되는 액세스 SharePoint [구성했습니다.](../security/office-365-security/sharepoint-file-access-policies.md)

다음으로, Contoso IT 관리자가 Project 2X라는 새 개인 팀을 만든 다음 Project 2X 직원의 사용자 계정을 구성원으로 추가했습니다. 또한 2X 팀 소유자만 비공개 채널을 Project 수 있도록 팀을 구성했습니다.

구성 세부 정보는 비공개 팀 [만들기를 참조합니다.](secure-teams-security-isolation.md#create-a-private-team)

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>2단계: Project 2X 팀에 대한 민감도 레이블 생성

Contoso 관리자는 **2X라는** 새 Project 레이블을 만들었다.

- 암호화를 사용하도록 설정했습니다.
- 2X Co-Author 2X 그룹에 Project 권한을 Microsoft 365 있습니다.
- Senior Leadership 그룹에 대한 보기 권한 허용
- 관리되지 않는 장치에 대한 액세스가 차단되었습니다.

기본 2X Project 문서 섹션의 SharePoint 다음을 통해 보호됩니다. 

- 사이트 사용 권한 - Project 2X 그룹의 구성원에게만 모든 Microsoft 365 권한 및 Senior Leadership 그룹에 대한 읽기 권한만 허용합니다.
- 이 Project 이동하거나 사이트에서 복사하는 경우 파일과 함께 이동하는 암호화 및 사용 권한이 있는 2X 민감도 레이블입니다.

구성 세부 정보는 민감도 레이블 [만들기를 참조합니다.](secure-teams-security-isolation.md#create-a-sensitivity-label)

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>3단계: 기본 사이트 SharePoint 구성

먼저, 팀의 기본 SharePoint 사이트에 대한 액세스를 보호하기 위해 Contoso IT 관리자는 권장되는 액세스 SharePoint [구성했습니다.](../security/office-365-security/sharepoint-file-access-policies.md)

다음으로 사이트에 대한 추가 사용 권한 설정을 구성했습니다.

- 2X Project 구성원이 사이트에 대한 액세스를 공유하지 못하게 합니다. 구성 세부 정보는 보안 SharePoint 팀에 대한 설정 [설정을 참조하세요.](secure-teams-security-isolation.md#sharepoint-settings)
- 선임 리더십 그룹에 대한 읽기 권한

그런 다음 2X 그룹 구성원이 사이트에 대한 액세스를 공유하지 못하도록 Project 추가 권한 설정을 구성했습니다. 

2X에 대한 비공개 채널이 Project 그룹 소유자가 게스트 공유를 사용하지 않도록 설정하고 기본 공유 링크를 **특정** 사용자 값으로 설정했습니다.

다음은 보안이 Project 2X 팀의 결과 구성입니다.

![2X 팀의 결과 Project 구성입니다.](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>4단계: 교육된 Project 2X 팀 구성원

Contoso 보안 직원은 다음을 Project 필수 과정에 2X 팀 구성원을 교육했습니다.

- 새 2X Project 액세스하고, 모임 및 채팅을 사용하며, 팀 파일을 공동으로 작업하는 방법
- 팀에서 새 파일을 만들고 로컬에서 만든 새 파일을 업로드하는 방법
- 2X 민감도 레이블을 Project 레이블을 지정하는 방법
- 2X 레이블이 팀을 떠날 Project 2X 레이블이 파일을 보호하는 방법에 대한 데모입니다.

최종적으로는 2X 팀 구성원이 채팅Project 모임 및 파일을 위한 안전한 환경에서 공동 작업을 하는 안전한 환경이되었습니다.

다음은 2X 민감도 레이블이 할당된 Project 2X 사이트에 Project 예입니다.

![2X 사이트에 저장된 파일의 Project 예제입니다.](../media/contoso-team-for-top-secret-project-example.png)

몇 가지 경우에 Project 2X 팀 구성원이 오프라인 작업을 위해 Project 2X 레이블로 보호된 파일을 로컬 드라이브에 다운로드했습니다. 

그러나 자격 증명을 열 때 자격 증명을 입력하라는 메시지가 표시되면 실수를 실현하고 삭제했습니다.

Teams 환경과 Microsoft 365 기능 때문에 Project 2X의 세부 정보는 프로젝트 기간 동안 비밀로 유지되었습니다. Contoso는 계획을 발표하고 고객 및 투자가의 즐거움과 경쟁업체를 위해 새로운 제품 및 서비스를 출시하는 중입니다.

## <a name="next-step"></a>다음 단계

[조직에 보안이 고지된](secure-teams-security-isolation.md) 팀을 배포합니다.

