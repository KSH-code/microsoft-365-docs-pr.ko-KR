---
title: 파일 포함
description: 포함 파일
author: mjcaparas
ms.service: microsoft-365-enterprise
ms.author: macapara
ms.openlocfilehash: e8d19f8ab5423ccc0441d29efab2ecdb3eb27a04
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60677196"
---
## <a name="prerequisites"></a>필수 구성 요소

끝점 시나리오용 Microsoft Defender의 보안 관리에 대한 요구 사항은 다음 섹션을 검토하세요.

### <a name="environment"></a>환경

장치가 끝점용 Microsoft Defender에 온보딩하는 경우:

- 디바이스가 Configuration Manager 또는 Intune의 기존 Endpoint Manager 설문 조사됩니다.
- 현재 Endpoint Manager 없는 장치를 사용하면 보안 관리 기능을 사용할 수 있습니다.
- 트러스트가 없는 Azure Active Directory 트러스트가 생성됩니다.
- Azure Active Directory 트러스트는 Endpoint Manager(Intune)와 통신하고 정책을 검색하는 데 사용됩니다.
- 정책에서 검색 Endpoint Manager Microsoft Defender for Endpoint에 의해 장치에 적용됩니다.

### <a name="active-directory-requirements"></a>Active Directory 요구 사항

도메인에 가입된 장치가 도메인과의 트러스트 Azure Active Directory 이 시나리오를 하이브리드 Azure Active Directory *조인 시나리오라고* 합니다. 끝점용 Microsoft Defender의 보안 관리는 다음 요구 사항을 충족하는 이 시나리오를 완벽하게 지원합니다.

- Azure Active Directory 커넥트 (AAD 커넥트)를 끝점용 Microsoft Defender에서 사용하는 테넌트와 동기화해야 합니다.
- 하이브리드 Azure Active Directory 조인은 사용자 환경에서(페더ation 또는 동기화를 통해) AAD 커넥트 구성해야 합니다.
- AAD 커넥트 동기화에서 장치 개체와  동기화하기 위해 범위에 장치 개체를 포함해야 Azure Active Directory(조인에 필요한 경우)
- AAD 커넥트 규칙은 Server 2012 R2에 대해 수정해야 합니다(Server 2012 R2에 대한 지원이 필요한 경우).

### <a name="connectivity-requirements"></a>연결 요구 사항

디바이스는 다음 끝점에 액세스할 수 있어야 합니다.

- `enterpriseregistration.windows.net` - Azure AD 등록의 경우.
- `login.microsoftonline.com` - Azure AD 등록의 경우.
- `*.dm.microsoft.com` - 와일드카드를 사용하는 경우 등록, 체크 인 및 보고에 사용되는 클라우드 서비스 끝점을 지원하며, 서비스 규모가 확장될 때 변경될 수 있습니다.

### <a name="supported-platforms"></a>지원되는 플랫폼

끝점용 Microsoft Defender 보안 관리 정책은 다음 장치 플랫폼에서 지원됩니다.

- [Windows 10 Professional/Enterprise(KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)사용)
- Windows Server 2012 Microsoft [Defender for Down-Level R2](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server 2016 [디바이스용 Microsoft Defender Down-Level 사용](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server [2019(KB5006744)](https://support.microsoft.com/topic/october-19-2021-kb5006744-os-build-17763-2268-preview-e043a8a3-901b-4190-bb6b-f5a4137411c0)
- Windows Server 2022


### <a name="licensing-and-subscriptions"></a>라이선스 및 구독

끝점용 Microsoft Defender에 대한 보안 관리를 사용하려면 다음이 필요합니다.

- Microsoft Defender for Endpoint용 라이선스(Microsoft 365) 또는 끝점용 Microsoft Defender에 대한 독립 실행형 라이선스를 부여하는 구독입니다. 옵션에 대한 최신 정보는 [끝점용 Microsoft Defender에 대한 최소 요구 사항을 참조하세요.](/microsoft-365/security/defender-endpoint/minimum-requirements)

  *또한* Microsoft Defender for Endpoint 라이선스를 부여하는 구독은 테넌트에 Microsoft Endpoint Manager 관리 센터의 끝점 보안 노드에 대한 액세스 권한을 부여합니다. 끝점 보안 노드에서는 디바이스에 대한 끝점용 Microsoft Defender를 관리하고 장치 상태를 모니터링하는 정책을 구성하고 배포할 수 있습니다.

## <a name="architecture"></a>아키텍처

다음 다이어그램은 끝점용 Microsoft Defender 보안 구성 관리 솔루션을 개념적으로 나타났습니다.


:::image type="content" alt-text="끝점용 Microsoft Defender 보안 구성 관리 솔루션의 개념 표현" source="../security/defender-endpoint/images/mde-architecture.png":::


1. 끝점용 Microsoft Defender에 장치 온보딩

2. 각 장치와 Azure AD 간에 트러스트가 설정됩니다. 장치에 기존 트러스트가 있는 경우 사용됩니다. 장치가 등록되지 않은 경우 새 트러스트가 만들어집니다.


3. 장치는 Azure AD ID를 사용하여 사용자와 통신할 Endpoint Manager. 이 ID를 Microsoft Endpoint Manager 장치를 대상으로 하는 정책을 배포할 수 있습니다.

4. Endpoint용 Defender는 정책의 상태를 다시 정책에 Endpoint Manager.

## <a name="configure-your-tenant-to-support-microsoft-defender-for-endpoint-security-configuration-management"></a>끝점 보안 구성 관리에 대한 Microsoft Defender를 지원하도록 테넌트 구성

Microsoft Endpoint Manager 관리 센터를 통해 끝점 보안 구성 관리를 위한 Microsoft Defender를 지원하려면 각 콘솔 내에서 해당 보안 구성 Microsoft Endpoint Manager 통신을 사용하도록 설정해야 합니다.

1. Microsoft 365 Defender 포털에 [로그인하고](https://security.microsoft.com/) 설정 끝점 구성 관리 적용 범위로 이동하여 보안 설정 관리를 위해 플랫폼을 사용하도록  >    >    >   설정하세요.

   :::image type="content" source="../media/enable-mde-settings-management-defender.png" alt-text="Defender 콘솔에서 끝점 설정 관리에 대해 Microsoft Defender를 사용하도록 설정하세요.":::

2. Defender 포털에서 역할을 구성하여 관련 사용자에게 Microsoft Endpoint Manager 보안 설정을 관리할 수 있는 권한이 있는지 확인합니다. 역할 **설정**  >  **항목**  >  **추가로 이동 :**

   :::image type="content" source="../media/add-role-in-mde.png" alt-text="Defender 포털에서 새 역할을 생성합니다.":::

   > [!TIP]
   > 기존 역할을 수정하고 끝점용 Microsoft Defender에서 추가 역할을 만드는 대신 필요한 사용 권한을 추가할 수 있습니다.

3. 역할을 구성할 때 사용자를 추가하고 에서 끝점 보안 설정 **관리를 선택해야 Microsoft Endpoint Manager.**

   :::image type="content" source="../media/add-role.png" alt-text="사용자에게 설정 관리 권한을 부여합니다.":::

4. [Microsoft Endpoint Manager 관리 센터](https://go.microsoft.com/fwlink/?linkid=2109431)에 로그인합니다.

5. **끝점 보안** Microsoft Defender for Endpoint를 선택하고 끝점용 Microsoft Defender가 끝점 보안 구성을 적용하도록 허용(미리  >   **보기)을** 으로 **설정합니다.**

   :::image type="content" source="../media/enable-mde-settings-management-mem.png" alt-text="관리 센터에서 끝점 설정 관리에 대해 Microsoft Defender를 Microsoft Endpoint Manager 활성화합니다.":::

   이 옵션을 *으로* 설정하면 사용자가 관리하지 않는 끝점용 Microsoft Defender의 플랫폼 범위에 Microsoft Endpoint Manager 끝점용 Microsoft Defender에 온보딩할 수 있습니다.

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender에 장치 온보딩

끝점용 Microsoft Defender는 장치를 온보딩하는 여러 옵션을 지원합니다. 현재 지침은 끝점용 Defender 설명서에서 Windows 장치용 [온보딩](/microsoft-365/security/defender-endpoint/security-config-management) 도구 및 방법을 참조하세요.

Intune 또는 Configuration Manager로 관리하는 장치는 이 시나리오에서 지원되지 않습니다.

## <a name="create-azure-ad-groups"></a>Azure AD 그룹 만들기

장치가 Endpoint용 Defender에 온보딩된 후 끝점용 Microsoft Defender에 대한 정책 배포를 지원하기 위한 장치 그룹을 만들어야 합니다.

끝점용 Microsoft Defender에 등록했지만 Intune 또는 Configuration Manager에서 관리되지 않는 장치를 식별하려면

1. [Microsoft Endpoint Manager 관리 센터](https://go.microsoft.com/fwlink/?linkid=2109431)에 로그인합니다.

2. 장치 모든 **장치로** 이동한 다음 관리되는 열을 선택하여 디바이스  >  보기를  정렬합니다.

   끝점용 Microsoft Defender에 등록되어 등록되어 있지만 Intune 또는 Configuration Manager에서 관리되지 않는 장치는 관리형 열에 **끝점용 Microsoft Defender를** *표시합니다.* 끝점용 Microsoft Defender에 대한 보안 관리 정책을 받을 수 있는 장치입니다.

[Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) 또는 2016 관리 센터 내에서 이러한 디바이스에 대한 [그룹을 Microsoft Endpoint Manager 있습니다.](/mem/intune/fundamentals/groups-add)

## <a name="deploy-policy"></a>정책 배포

끝점용 Microsoft Defender에서 관리하는 장치를 포함하는 Azure AD 그룹을 하나 이상 만든 후 끝점용 Microsoft Defender의 보안 관리에 대한 다음 정책을 만들고 해당 그룹에 배포할 수 있습니다.

- 바이러스 검사
- 방화벽
- 방화벽 규칙
- 끝점 검색 및 응답

> [!TIP]
> 동일한 설정을 관리하는 여러 정책을 장치에 배포하지 않도록 합니다.
>
> Microsoft Endpoint Manager 각 끝점 보안 정책 유형의 여러 인스턴스를 동일한 장치에 배포할 수 있습니다. 각 정책 인스턴스는 장치에서 별도로 수신됩니다. 따라서 장치가 서로 다른 정책에서 동일한 설정에 대해 별도의 구성을 수신할 수 있으므로 충돌이 일어날 수 있습니다. 일부 설정(예: 바이러스 백신 제외)은 클라이언트에서 병합된 후 성공적으로 적용됩니다.

1. [Microsoft Endpoint Manager 관리 센터](https://go.microsoft.com/fwlink/?linkid=2109431)에 로그인합니다.

2. **끝점 보안으로 이동한** 다음 구성할 정책 유형(바이러스 백신 또는 방화벽)을 선택한 다음 정책 만들기 **를 선택합니다.**

3. 다음 속성 또는 선택한 정책 유형을 입력합니다.

   - 바이러스 백신 정책에 대해 다음을 선택합니다.
     - 플랫폼: Windows 10, Windows 11 및 Windows **서버(미리 보기)**
     - 프로필: **Microsoft Defender 바이러스 백신(미리 보기)**

   - 방화벽 정책에 대해 다음을 선택합니다.
     - 플랫폼: Windows 10, Windows 11 및 Windows **서버(미리 보기)**
     - 프로필: **Microsoft Defender 방화벽(미리 보기)**

   - 방화벽 규칙 정책에 대해 다음을 선택합니다.
     - 플랫폼: Windows 10, Windows 11 및 Windows **서버(미리 보기)**
     - 프로필: **Microsoft Defender 방화벽 규칙(미리 보기)**

   - 끝점 검색 및 응답 정책에 대해 다음을 선택합니다.
     - 플랫폼: Windows 10, Windows 11 및 Windows **서버(미리 보기)**
     - 프로필: **끝점 검색 및 응답(미리 보기)**

4. **만들기** 를 선택합니다.

5. 기본 **페이지에서** 프로필의 이름과 설명을 입력한 후 다음 을 **선택합니다.**

6. 구성 **설정 페이지에서** 이 프로필로 관리할 설정을 선택합니다. 설정에 대한 자세한 내용을 확인하려면 해당  정보 대화 상자를 확장하고 자세한 정보 링크를 선택하여 해당 설정에 대한 CSP 정보를 참조하세요.

   설정 구성을 완료하면 **다음** 을 선택합니다.

7. 할당 **페이지에서** 이 프로필을 받을 Azure AD 그룹을 선택합니다. 프로필 할당에 대한 자세한 내용은 [사용자 및 디바이스 프로필 할당](/mem/intune/configuration/device-profile-assign)을 참조하세요.

   **다음** 을 선택하여 계속합니다.

   > [!TIP]
   >
   > - 보안 구성 관리 프로필에는 할당 필터가 지원되지 않습니다.
   > - Endpoint용 Microsoft Defender 관리에는 Device *개체만* 적용할 수 있습니다. 사용자 대상 지정은 지원되지 않습니다.
   > - 구성된 정책은 Microsoft Intune 및 끝점 클라이언트용 Microsoft Defender 둘 다에 적용됩니다.

8. 정책 만들기 프로세스를 완료한 다음 검토 **+** 만들기 페이지에서 만들기를 **선택합니다.** 사용자가 만든 프로필에 대한 정책 유형을 선택하면 목록에 새 프로필이 표시됩니다.

9. 정책이 할당될 때까지 기다렸다가 정책이 적용되었다는 표시가 성공한 것으로 표시됩니다.

10. [Get-MpPreference](/powershell/module/defender/get-mppreference#examples) 명령 유틸리티를 사용하여 클라이언트에 로컬로 설정이 적용되는지 확인할 수 있습니다.

