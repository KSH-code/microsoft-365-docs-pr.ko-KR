---
title: Microsoft OneDrive
description: 등록된 Microsoft Managed Desktop 대한 OneDrive 설정하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB 앱, LOB 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a599f36692cbca6cbf67ddfd4a6ca1c05e02351f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60214036"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Managed Desktop [장치를](/onedrive/plan-onedrive-enterprise) 비즈니스용 OneDrive 위해 모든 Microsoft Managed Desktop 저장소 서비스로 사용하여 장치가 상태 비저장 상태이지 않도록 합니다. 사용자는 로그인한 디바이스에 상관없이 파일을 찾을 수 있습니다. 예를 들어 Microsoft Managed Desktop 장치를 새 장치로 바꾸면 파일이 새 장치와 자동으로 동기화됩니다.

Microsoft Managed Devices에서 기본적으로 이러한 설정을 자동으로 구성합니다.

- OneDrive 계정으로 자동으로 구성되며 사용자 조작 없이 사용자 계정에 로그인하는 데 사용된 사용자 계정에 Windows. 자세한 내용은 자동 사용자 계정 구성 [-](/onedrive/use-silent-account-configuration) OneDrive

- 사용자가 디스크 공간을 불필요하게 사용하지 않고도 클라우드 저장소의 클라우드 저장소에서 파일에 액세스할 수 있도록 OneDrive 필요 시 파일 관리 기능을 사용할 수 있습니다. 자세한 내용은 에 대한 OneDrive 파일 OneDrive 디스크 [공간 저장을 Windows 10.](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)

- 알려진 폴더 이동 기능은 클라우드에서 사용자의 데이터를 백업할 수 있도록 자동으로 사용하도록 설정되어 모든 장치에서 파일에 액세스할 수 있습니다. 자세한 내용은 [Back up your Documents, Pictures, and Desktop folders with OneDrive.](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)

- 사용자는 알려진 폴더 이동 기능을 사용하지 않도록 설정하거나 알려진 폴더의 위치를 변경하여 여러 장치에서 일관된 환경을 Microsoft Managed Desktop 없습니다.

## <a name="user-experience"></a>사용자 환경

사용자가 Microsoft Managed Desktop 장치를 받는 경우 장치를 설정하는 동안 Azure 자격 증명을 입력하여 첫 실행 환경을 진행합니다. 이 프로세스가 완료된 후 데스크톱에 액세스하여 사용자 환경을 OneDrive 있습니다.

1. 시스템은 사용자가 구성한 OneDrive 사용자가 자동으로 로그인되어 있는지를 사용자에게 OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="이제 동기화 중일 때 읽은 OneDrive 파일을 편집할 수 OneDrive. 파일을 보려면 여기를 클릭합니다.":::

2. 시스템에서 알려진 폴더 이동이 OneDrive 사용자에게 알 수 있습니다.

:::image type="content" source="media/onedrive-folders.png" alt-text="알림 IT 부서에서 중요한 폴더를 백업했습니다. 이제 폴더가 백업되어 OneDrive 장치에서 사용할 수 있습니다.":::

3. 장치가 초기화되거나 다시 디자인될 때 바탕 화면에서 중복 아이콘을 방지하기 위해 시스템은 파일 탐색기에서 이 보기에 표시된 Microsoft Edge Microsoft Teams 아이콘을 OneDrive 동기화 제거합니다.

:::image type="content" source="media/onedrive-teams.png" alt-text="선택 취소된 Teams 및 마우스로 텍스트를 마우스로 읽은 후 동기화에서 제외된 목록을 표시하는 파일 탐색기입니다.":::


## <a name="onedrive-sync-restrictions"></a>OneDrive 동기화 제한 사항

제한해야 하는 OneDrive 동기화 조건부 액세스 정책을 사용하여 액세스를 Azure Active Directory 것이 좋습니다. 자세한 내용은 앱의 조건부 액세스 지원 OneDrive 동기화 [참조하세요.](/onedrive/enable-conditional-access)

조직에서 Azure AD 조건부 액세스 정책을 사용할 수 없는 경우 IT 관리자는 다음 단계를 따라야 합니다.

1. 아직 모르는 경우 Find your Microsoft 365 tenant ID 에 설명된 [테넌트 ID를 찾아보세요.](/onedrive/find-your-office-365-tenant-id)
2. OneDrive 센터에 로그인한 다음 왼쪽 창에서 **동기화를** 선택합니다. 특정 도메인에 가입된 **PC에서만** 동기화 허용 확인란을 선택한 다음 도메인 목록에 테넌트 ID를 추가합니다. 자세한 내용은 특정 도메인에 가입된 컴퓨터에서만 동기화 [허용을 참조하세요.](/onedrive/allow-syncing-only-on-specific-domains)

> [!NOTE]
> 이 지침은 해당 정책의 테넌트에만 Microsoft Managed Desktop. 이 문서에서 설명하지 않는 다른 설정이 사용 중입니다.