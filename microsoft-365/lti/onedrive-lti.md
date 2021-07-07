---
title: 도구 Microsoft OneDrive Learning 사용
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 과제를 만들고 등급을 지정하고, 과정 콘텐츠를 작성 및 구성하고, 새로운 Microsoft OneDrive Learning 도구 상호 관리 앱을 사용하여 실시간으로 파일을 공동 작업합니다.
ms.openlocfilehash: bcb374ed1666f23fa5f3d4692f43a4369670e891
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322224"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="7f23f-103">Canvas Microsoft OneDrive LTI 통합</span><span class="sxs-lookup"><span data-stu-id="7f23f-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="7f23f-104">LTI를 Microsoft OneDrive 통합하는 과정은 두 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="7f23f-105">첫 번째 단계에서는 Canvas에서 Microsoft OneDrive 사용할 수 있으며, 두 번째 단계에서는 Canvas Microsoft OneDrive LTI를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="7f23f-106">권장 브라우저 설정</span><span class="sxs-lookup"><span data-stu-id="7f23f-106">Recommended browser settings</span></span>

- <span data-ttu-id="7f23f-107">쿠키를 사용할 수 Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7f23f-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="7f23f-108">팝업은 차단하지 말아야 Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7f23f-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="7f23f-109">쿠키는 Chrome 브라우저의 시그니치 모드에서 기본적으로 사용하도록 설정되지 않습니다. 이 경우 쿠키를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="7f23f-110">Microsoft OneDrive LTI는 브라우저의 개인 모드에서 Microsoft Edge 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="7f23f-111">기본적으로 사용하도록 설정된 쿠키를 차단하지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="7f23f-112">Canvas에서 Microsoft OneDrive LTI 사용</span><span class="sxs-lookup"><span data-stu-id="7f23f-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f23f-113">이 통합을 수행하는 사람은 Canvas의 관리자이자 테넌트의 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="7f23f-114">LTI Microsoft OneDrive <a href="https://onedrivelti.microsoft.com/admin" target="_blank">포털에 로그인합니다.</a></span><span class="sxs-lookup"><span data-stu-id="7f23f-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="7f23f-115">관리자 **동의 단추를** 선택하고 사용 권한을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-115">Select the **Admin Consent** button and accept the permissions.</span></span>

> [!CAUTION]
> <span data-ttu-id="7f23f-116">이 단계를 수행하지 않은 경우 다음 단계를 수행하면 오류가 발생하고 한 시간 동안 이 단계를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-116">If this step isn't performed, the following step will give you an error, and you won't be able to take this step for an hour once you've gotten the error.</span></span>

3. <span data-ttu-id="7f23f-117">새 **LTI 테넌트 만들기 단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-117">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="7f23f-118">LTI 등록 페이지에서 드롭다운에서 **캔버스를** 선택하고 Canvas 인스턴스의 기본 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-118">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="7f23f-119">Canvas 인스턴스가 ]()인 경우 https://contoso.test.instructure.com https://contoso.test.instructure.com) 전체 URL을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-119">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="LTI 소비자 플랫폼 및 URL 텍스트 필드를 선택하기 위한 드롭다운 필드가 있는 LTI 테넌트 관리 페이지":::

4. <span data-ttu-id="7f23f-121">복사 단추(오른쪽에 두  페이지를 표시하는 아이콘)를 선택하여 JSON을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-121">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="7f23f-122">이 키는 Canvas에서 키를 생성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-122">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="표시된 JSON 텍스트를 복사하고 Canvas에서 키 생성에 사용할 수 있도록 하는 복사 단추를 보여 주는 이미지입니다.":::

5. <span data-ttu-id="7f23f-124">관리자 권한으로 Canvas 인스턴스에  로그인하고 페이지 왼쪽 메뉴에서 개발자 키를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-124">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="7f23f-125">드롭다운에서 페이지 오른쪽 위에 있는 드롭다운에서 **LTI** 키를 선택하여 개발자 키를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="7f23f-125">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="개발자 키가 선택된 왼쪽 탐색 모음과 페이지 오른쪽의 드롭다운에서 LTI 키 항목을 선택한 스크린샷":::

6. <span data-ttu-id="7f23f-127">구성 페이지의 메서드 드롭다운에서 **메서드로 JSON** 붙여넣기 를 선택하고 5단계에서 복사한 JSON 텍스트를 나타나는 텍스트 필드에 붙여 넣습니다. </span><span class="sxs-lookup"><span data-stu-id="7f23f-127">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="7f23f-128">키를 저장하면 Canvas에서 Off 상태로 사용할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-128">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="7f23f-129">키를 **켜고** 다음 단계에서 사용할  세부 정보 열에 제공된 키를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-129">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="키가 꺼진 상태로 설정된 Canvas 페이지입니다. 이 키를 켜야 합니다. 이 페이지의 세부 정보 열에서 키를 복사해야 합니다.":::

8. <span data-ttu-id="7f23f-131">LTI Microsoft OneDrive 포털로 돌아가 캔버스 클라이언트 ID 필드에 키를 **붙여 넣습니다.**</span><span class="sxs-lookup"><span data-stu-id="7f23f-131">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="7f23f-132">준비가 **되면** 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-132">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="키를 복사해야 하는 JSON 텍스트와 텍스트 상자를 보여 주며 LTI 테넌트 등록 페이지입니다.":::

9. <span data-ttu-id="7f23f-134">변경 내용을 검토하고 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-134">Review and save your changes.</span></span> <span data-ttu-id="7f23f-135">성공적인 등록 시 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-135">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="7f23f-136">홈 페이지에서 **LTI** 테넌트 보기 단추를 선택하여 등록 세부 정보를 검토할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-136">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="7f23f-137">Canvas Microsoft OneDrive LTI 사용</span><span class="sxs-lookup"><span data-stu-id="7f23f-137">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="7f23f-138">Canvas 관리자는 모든 Microsoft OneDrive LTI를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-138">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="7f23f-139">특정 Microsoft OneDrive LTI가 필요한 경우(모든 과정이 아닌) 강사는 과정 설정 내에서 동일한 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-139">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="7f23f-140">관리자로 로그인하고 설정 **섹션으로** 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="7f23f-140">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="7f23f-141">앱 **섹션으로 이동하여** 앱 구성 보기 **단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-141">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="7f23f-142">앱 **추가 단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-142">Select the **Add App** button.</span></span>
4. <span data-ttu-id="7f23f-143">구성 **유형 드롭다운에서** 클라이언트 **ID 옵션을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-143">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="7f23f-144">이전에 클라이언트 ID 필드에 생성된 개발자 키 값을 **붙여넣고** 제출 **단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-144">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="구성 유형 드롭다운 메뉴 아래에 클라이언트 ID 옵션을 표시하는 앱 추가 페이지입니다.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="7f23f-146">Canvas 설정 LTI에 Microsoft OneDrive 대한 공동 작업 작업</span><span class="sxs-lookup"><span data-stu-id="7f23f-146">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="7f23f-147">교육자 및 학생을 위해 공동 작업을 진행하려면 공동 작업 설정을 사용하도록 설정하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-147">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="7f23f-148">설정이 사용하도록 설정되어 있지 않은지 확인을 위해 아래 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="7f23f-148">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="7f23f-149">관리자로 로그인하고 설정 **섹션으로** 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="7f23f-149">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="7f23f-150">기능 옵션 **섹션으로** 이동한 다음 과정 **섹션으로** 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="7f23f-150">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="7f23f-151">외부 공동 **작업 도구** 기능을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-151">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="7f23f-152">개별 학생 및 학생 그룹에 공동 작업을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-152">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="7f23f-153">개별 학생에게 할당은 기본적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-153">Assigning to individual students works by default.</span></span> <span data-ttu-id="7f23f-154">학생 그룹에 공동 작업을 할당할 수 있는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f23f-154">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="7f23f-155">관리자로 로그인하고 개발자 키 **섹션으로** 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="7f23f-155">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="7f23f-156">값이 170000000000710인 키를 찾아 On으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="7f23f-156">Find the key with value 170000000000710 and set it to **On**.</span></span>
