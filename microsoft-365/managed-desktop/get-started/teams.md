---
title: Microsoft Teams
description: 장치에 Teams 업데이트하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB 앱, LOB 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 525dc7b89e302cdc076336daa7a98c6317855e73
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60212740"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) 실시간 공동 [](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) 작업 및 통신, 모임, 파일 및 앱 공유를 위한 작업 영역도 제공하는 조직용 메시징 앱입니다.

## <a name="initial-deployment"></a>초기 배포

대부분의 하드웨어 공급업체는 아직 이미지의 일부로 Teams 포함하지 않았기 때문에 Microsoft Managed Desktop 사용하여 Teams 장치를 Microsoft Intune. 모든 관리되는 장치에는 Teams .msi 패키지가 설치되어 디바이스에 로그인하는 모든 사용자가 사용할 Microsoft Teams 수 있습니다. [](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) 패키지 설치가 처음 완료되면 Teams 자동으로 시작되고 바탕 화면에 바로 가기가 추가됩니다.

### <a name="microsoft-intune-changes"></a>Microsoft Intune 변경 내용

Microsoft Managed Desktop Azure AD 조직에 두 개의 응용 프로그램을 추가하여 Microsoft Teams. 디바이스에 따라 64비트 또는 32비트 클라이언트에 배포됩니다.  

- 최신 작업 공간 – Teams 컴퓨터 전체 설치 관리자 x64  
- 최신 작업 공간 – Teams 컴퓨터 전체 설치 관리자 x32

## <a name="updates"></a>업데이트

Teams 클라이언트와 별도의 업데이트 엔터프라이즈용 Microsoft 365 앱 따라가면 데스크톱 클라이언트가 자동으로 업데이트됩니다. Teams 몇 시간마다 업데이트를 확인하여 다운로드한 다음 컴퓨터가 유휴될 때까지 기다렸다가 업데이트를 자동으로 설치합니다.  

Teams 그룹에서는 관리자가 업데이트를 제어할 수 없습니다. 따라서 Microsoft Managed Desktop 채널이 [사용되지 않습니다.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)

### <a name="manually-updating-teams"></a>수동으로 업데이트 Teams

개별 사용자는 앱 오른쪽 상단의 프로필 드롭다운 메뉴에서 업데이트 확인을 선택하여 업데이트를 다운로드할    수도 ****   있습니다. 업데이트를 사용할 수 있는 경우 컴퓨터가 유휴일 때 자동으로 설치됩니다.

## <a name="delivery-optimization-of-updates"></a>업데이트 배달 최적화

Teams 업데이트에 대한 배달 최적화는 기본적으로 설정되어 있으며 관리자 또는 사용자의 작업이 필요 없습니다.