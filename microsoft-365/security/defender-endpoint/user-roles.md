---
title: 역할 기반 액세스 제어에 대한 역할 만들기 및 관리
description: 역할을 만들고 Microsoft Defender 보안 센터에서 역할 기반 액세스 제어 구현의 일부로 역할에 할당된 사용 권한을 정의합니다.
keywords: 사용자 역할, 역할, rbac 액세스
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073988"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a><span data-ttu-id="54fba-104">역할 기반 액세스 제어에 대한 역할 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="54fba-104">Create and manage roles for role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54fba-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="54fba-105">**Applies to:**</span></span>
- [<span data-ttu-id="54fba-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="54fba-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="54fba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54fba-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="54fba-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="54fba-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="54fba-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a><span data-ttu-id="54fba-110">역할을 만들고 Azure Active Directory 그룹에 역할 할당</span><span class="sxs-lookup"><span data-stu-id="54fba-110">Create roles and assign the role to an Azure Active Directory group</span></span>

<span data-ttu-id="54fba-111">다음 단계에서는 Microsoft Defender 보안 센터에서 역할을 만드는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-111">The following steps guide you on how to create roles in Microsoft Defender Security Center.</span></span> <span data-ttu-id="54fba-112">Azure Active Directory 사용자 그룹을 이미 만들었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-112">It assumes that you have already created Azure Active Directory user groups.</span></span>

1. <span data-ttu-id="54fba-113">보안 관리자 또는 전역 관리자 역할이 할당된 계정을 사용하여 [Microsoft Defender](https://securitycenter.windows.com/) 보안 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-113">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with a Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="54fba-114">탐색 창에서 설정 및 **> 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54fba-114">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="54fba-115">항목 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54fba-115">Select **Add item**.</span></span>

4. <span data-ttu-id="54fba-116">역할에 할당할 역할 이름, 설명 및 사용 권한을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-116">Enter the role name, description, and permissions you'd like to assign to the role.</span></span>

5. <span data-ttu-id="54fba-117">**다음을** 선택하여 Azure AD 보안 그룹에 역할을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-117">Select **Next** to assign the role to an Azure AD Security group.</span></span>

6. <span data-ttu-id="54fba-118">필터를 사용하여 이 역할에 추가할 Azure AD 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-118">Use the filter to select the Azure AD group that you'd like to add to this role to.</span></span>

7. <span data-ttu-id="54fba-119">**를 저장하고 닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="54fba-119">**Save and close**.</span></span>

8. <span data-ttu-id="54fba-120">구성 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-120">Apply the configuration settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54fba-121">역할을 만든 후 방금 만든 역할에 할당하여 장치 그룹을 만들고 장치 그룹에 대한 액세스를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-121">After creating roles, you'll need to create a device group and provide access to the device group by assigning it to a role that you just created.</span></span>

### <a name="permission-options"></a><span data-ttu-id="54fba-122">사용 권한 옵션</span><span class="sxs-lookup"><span data-stu-id="54fba-122">Permission options</span></span>

- <span data-ttu-id="54fba-123">**데이터 보기**</span><span class="sxs-lookup"><span data-stu-id="54fba-123">**View data**</span></span>
    - <span data-ttu-id="54fba-124">**보안 작업** - 포털의 모든 보안 작업 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="54fba-124">**Security operations** - View all security operations data in the portal</span></span>
    - <span data-ttu-id="54fba-125">**위협 및 취약성 관리** - 포털에서 위협 및 취약성 관리 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="54fba-125">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

- <span data-ttu-id="54fba-126">**활성 수정 작업**</span><span class="sxs-lookup"><span data-stu-id="54fba-126">**Active remediation actions**</span></span>
    - <span data-ttu-id="54fba-127">**보안 작업** - 대응 조치 수행, 보류 중인 수정 작업 승인 또는 해지, 자동화 및 표시기를 위한 허용/차단 목록 관리</span><span class="sxs-lookup"><span data-stu-id="54fba-127">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
    - <span data-ttu-id="54fba-128">**위협 및 취약성 관리 - 예외 처리 -** 새 예외 만들기 및 활성 예외 관리</span><span class="sxs-lookup"><span data-stu-id="54fba-128">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
    - <span data-ttu-id="54fba-129">**위협 및 취약성 관리 -** 수정 처리 - 새 수정 요청을 제출하고, 티켓을 만들고, 기존 수정 활동을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-129">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

- <span data-ttu-id="54fba-130">**경고 조사** - 경고 관리, 자동화된 조사 시작, 검사 실행, 조사 패키지 수집, 장치 태그 관리, PE(이식 가능한 실행 파일) 파일만 다운로드</span><span class="sxs-lookup"><span data-stu-id="54fba-130">**Alerts investigation** - Manage alerts, initiate automated investigations, run scans, collect investigation packages, manage device tags, and download only portable executable (PE) files</span></span> 

- <span data-ttu-id="54fba-131">**포털 시스템** 설정 관리 - 저장소 설정, SIEM 및 위협 인텔리전스 API 설정 구성(전역적으로 적용), 고급 설정, 자동화된 파일 업로드, 역할 및 장치 그룹</span><span class="sxs-lookup"><span data-stu-id="54fba-131">**Manage portal system settings** - Configure storage settings, SIEM and threat intel API settings (applies globally), advanced settings, automated file uploads, roles and device groups</span></span>

    > [!NOTE]
    > <span data-ttu-id="54fba-132">이 설정은 끝점 관리자용 Microsoft Defender(기본값) 역할에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-132">This setting is only available in the Microsoft Defender for Endpoint administrator (default) role.</span></span>

- <span data-ttu-id="54fba-133">**보안 센터에서** 보안 설정 관리 - 경고 제거 설정 구성, 자동화에 대한 폴더 제외 관리, 온보드 및 오프보드 장치, 전자 메일 알림 관리, 평가 랩 관리</span><span class="sxs-lookup"><span data-stu-id="54fba-133">**Manage security settings in Security Center** - Configure alert suppression settings, manage folder exclusions for automation, onboard and offboard devices, and manage email notifications, manage evaluation lab</span></span>

- <span data-ttu-id="54fba-134">**실시간 응답 기능**</span><span class="sxs-lookup"><span data-stu-id="54fba-134">**Live response capabilities**</span></span>
    - <span data-ttu-id="54fba-135">**기본** 명령:</span><span class="sxs-lookup"><span data-stu-id="54fba-135">**Basic** commands:</span></span>
        - <span data-ttu-id="54fba-136">라이브 응답 세션 시작</span><span class="sxs-lookup"><span data-stu-id="54fba-136">Start a live response session</span></span>
        - <span data-ttu-id="54fba-137">원격 디바이스에서 읽기 전용 라이브 응답 명령 수행(파일 복사 및 실행 제외)</span><span class="sxs-lookup"><span data-stu-id="54fba-137">Perform read only live response commands on remote device (excluding file copy and execution</span></span>
    - <span data-ttu-id="54fba-138">**고급** 명령:</span><span class="sxs-lookup"><span data-stu-id="54fba-138">**Advanced** commands:</span></span>
        - <span data-ttu-id="54fba-139">라이브 응답을 통해 원격 장치에서 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="54fba-139">Download a file from the remote device via live response</span></span>
        - <span data-ttu-id="54fba-140">파일 페이지에서 PE 및 PE가 아닌 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="54fba-140">Download PE and non-PE files from the file page</span></span>
        - <span data-ttu-id="54fba-141">원격 장치에 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="54fba-141">Upload a file to the remote device</span></span>
        - <span data-ttu-id="54fba-142">파일 라이브러리에서 스크립트 보기</span><span class="sxs-lookup"><span data-stu-id="54fba-142">View a script from the files library</span></span>
        - <span data-ttu-id="54fba-143">파일 라이브러리에서 원격 디바이스에서 스크립트 실행</span><span class="sxs-lookup"><span data-stu-id="54fba-143">Execute a script on the remote device from the files library</span></span>

<span data-ttu-id="54fba-144">사용 가능한 명령에 대한 자세한 내용은 Live 응답을 사용하여 [장치 조사를 참조하세요.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="54fba-144">For more information on the available commands, see [Investigate devices using Live response](live-response.md).</span></span>
  
## <a name="edit-roles"></a><span data-ttu-id="54fba-145">역할 편집</span><span class="sxs-lookup"><span data-stu-id="54fba-145">Edit roles</span></span>

1. <span data-ttu-id="54fba-146">보안 관리자 또는 전역 관리자 역할이 할당된 계정을 사용하여 [Microsoft Defender](https://securitycenter.windows.com/) 보안 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-146">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="54fba-147">탐색 창에서 설정 및 **> 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54fba-147">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="54fba-148">편집할 역할을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-148">Select the role you'd like to edit.</span></span>

4. <span data-ttu-id="54fba-149">**편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-149">Click **Edit**.</span></span>

5. <span data-ttu-id="54fba-150">역할에 할당된 그룹 또는 세부 정보를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-150">Modify the details or the groups that are assigned to the role.</span></span> 

6. <span data-ttu-id="54fba-151">저장을 **클릭하고 를 닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="54fba-151">Click **Save and close**.</span></span>

## <a name="delete-roles"></a><span data-ttu-id="54fba-152">역할 삭제</span><span class="sxs-lookup"><span data-stu-id="54fba-152">Delete roles</span></span>

1. <span data-ttu-id="54fba-153">보안 관리자 또는 전역 관리자 역할이 할당된 계정을 사용하여 [Microsoft Defender](https://securitycenter.windows.com/) 보안 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-153">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="54fba-154">탐색 창에서 설정 및 **> 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54fba-154">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="54fba-155">삭제할 역할을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="54fba-155">Select the role you'd like to delete.</span></span>

4. <span data-ttu-id="54fba-156">드롭다운 단추를 클릭하고 역할 **삭제 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="54fba-156">Click the drop-down button and select **Delete role**.</span></span>

## <a name="related-topic"></a><span data-ttu-id="54fba-157">관련 항목</span><span class="sxs-lookup"><span data-stu-id="54fba-157">Related topic</span></span>

- [<span data-ttu-id="54fba-158">포털에 액세스하기 위한 사용자 기본 권한</span><span class="sxs-lookup"><span data-stu-id="54fba-158">User basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="54fba-159">장치 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="54fba-159">Create and manage device groups</span></span>](machine-groups.md)
