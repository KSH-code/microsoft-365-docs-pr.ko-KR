---
title: LinkedIn 데이터를 보관할 커넥터 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 관리자가 기본 커넥터를 사용하여 LinkedIn 회사 & 데이터를 가져오는 방법을 Microsoft 365.
ms.openlocfilehash: 70d17c0cf9eaeec7110ea178f1f3db56c3d3b553
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60167501"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>LinkedIn 데이터를 보관할 커넥터 설정

연결선의 커넥터를 Microsoft 365 규정 준수 센터 LinkedIn 회사 페이지에서 데이터를 가져오고 보관할 수 있습니다. 커넥터를 설정하고 구성한 후 24시간마다 한 번씩 특정 LinkedIn Company 페이지의 계정에 연결합니다. 커넥터는 회사 페이지에 게시된 메시지를 전자 메일 메시지로 변환한 다음 해당 항목을 회사에 있는 사서함으로 Microsoft 365.

LinkedIn 회사 페이지 데이터가 사서함에 저장되고 나면 소송 보존, Microsoft 365 검색, In-Place 보관, 감사 및 보존 정책과 같은 Microsoft 365 규정 준수 기능을 LinkedIn 데이터에 적용할 수 있습니다. 예를 들어 콘텐츠 검색을 사용하여 이러한 항목을 검색하거나 저장소 사서함을 보관된 사례에 Advanced eDiscovery 있습니다. 조직에서 LinkedIn 데이터를 가져오고 보관하는 커넥터를 Microsoft 365 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.

## <a name="before-you-set-up-a-connector"></a>커넥터를 설정하기 전에

- LinkedIn 회사 페이지 커넥터를 만드는 사용자에게 사서함 가져오기 내보내기 역할이 할당되어야 Exchange Online. 이 연결은 서버의 데이터  커넥터 페이지에서 커넥터를 추가하는 Microsoft 365 규정 준수 센터. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. 사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online. 또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.

- 보관할 LinkedIn 회사 페이지의 관리자인 LinkedIn 사용자 계정의 로그인 자격 증명(전자 메일 주소 또는 전화 번호 및 암호)이 있어야 합니다. 커넥터를 설정할 때 이러한 자격 증명을 사용하여 LinkedIn에 로그인합니다.

- LinkedIn 커넥터는 하루 총 200,000개 항목을 가져올 수 있습니다. 하루 200,000개가 넘는 LinkedIn 항목이 있는 경우 이러한 항목 중 어떤 항목도 가져오지 Microsoft 365.

## <a name="create-a-linkedin-connector"></a>LinkedIn 커넥터 만들기

1. 으로 <https://compliance.microsoft.com> 이동한 다음 **데이터** 커넥터  >  **LinkedIn 회사 페이지 를 클릭합니다.**

2. **LinkedIn 회사 페이지 제품** 페이지에서 커넥터 **추가를 클릭합니다.**

3. 서비스 **약관 페이지에서** 수락을 **선택합니다.**

4. **LinkedIn으로 로그인 페이지에서 LinkedIn으로** **로그인을 클릭합니다.**

   LinkedIn 로그인 페이지가 표시됩니다.

   ![LinkedIn 로그인 페이지.](../media/LinkedInSigninPage.png)

5. LinkedIn 로그인 페이지에서 보관할 회사 페이지와 연결된 LinkedIn 계정의 전자 메일 주소(또는 전화 번호)와 암호를 입력한 다음 **로그인을 클릭합니다.**

   로그인한 계정과 연결된 모든 LinkedIn 회사 페이지 목록과 함께 마법사 페이지가 표시됩니다. 커넥터는 한 회사 페이지에만 구성할 수 있습니다. 조직에 LinkedIn 회사 페이지가 여러 개 있는 경우 각 페이지에 대한 커넥터를 만들어야 합니다.

   ![LinkedIn 회사 페이지 목록이 있는 페이지가 표시됩니다.](../media/LinkedInSelectCompanyPage.png)

6. 항목을 보관할 회사 페이지를 선택하고 다음 을 **클릭합니다.**

7. 저장소 **위치 선택 페이지에서** 상자를 클릭하고 LinkedIn 항목을 가져올 Microsoft 365 사서함의 전자 메일 주소를 선택한 후 다음 을 **클릭합니다.** 항목이 이 사서함의 받은 편지함 폴더로 가져오기됩니다.

8. **다음을** 클릭하여 커넥터 설정을 검토한 다음 마친을 클릭하여 커넥터 설정을 완료합니다. 

커넥터를 만든 후 데이터 커넥터 페이지로 돌아가 새 커넥터의 가져오기 프로세스 진행률을  볼 수 있습니다(커넥터 목록을 업데이트하는 데 필요한 경우 새로 고침을 선택합니다).  상태 **열의 값은** **시작 대기 중입니다.** 초기 가져오기 프로세스를 시작하는 데 최대 24시간이 소요됩니다. 커넥터가 처음으로 실행되고 LinkedIn 항목을 가져오면 커넥터가 24시간마다 한 번씩 실행되고 지난 24시간 동안 LinkedIn 회사 페이지에 만들어진 새 항목을 가져올 수 있습니다.

자세한 내용을 확인하려면 데이터 커넥터 페이지의 목록에서 커넥터를 **선택하여** 플라이아웃 페이지를 표시합니다. 상태 **아래에서** 표시되는 날짜 범위는 커넥터를 만들 때 선택된 기간 필터를 나타냅니다.

## <a name="more-information"></a>추가 정보

LinkedIn 항목은 연결된 저장소 사서함의 받은 편지함에 있는 LinkedIn 하위 Microsoft 365. 전자 메일 메시지로 표시됩니다.