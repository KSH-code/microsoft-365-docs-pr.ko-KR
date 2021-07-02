---
title: 도구 OneDrive Learning 사용
ms.author: v-cichur
author: cichur
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
description: 과제를 만들고 등급을 지정하고, 과정 콘텐츠를 작성 및 구성하고, 새로운 OneDrive Learning 도구 상호 관리 앱을 사용하여 실시간으로 파일을 공동으로 작업합니다.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256987"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="7b30b-103">Canvas에서 Microsoft OneDrive LTI 사용</span><span class="sxs-lookup"><span data-stu-id="7b30b-103">Use Microsoft OneDrive LTI with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b30b-104">일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7b30b-105">Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="integrate-with-canvas"></a><span data-ttu-id="7b30b-106">Canvas와 통합</span><span class="sxs-lookup"><span data-stu-id="7b30b-106">Integrate with Canvas</span></span>

<span data-ttu-id="7b30b-107">이 통합을 수행하는 사용자는 Canvas의 관리자이자 테넌트의 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-107">The person who performs this integration should be an admin of Canvas and an admin of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="7b30b-108">테넌트 관리자 계정으로 Microsoft Azure 포털에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-108">Sign in to the Microsoft Azure portal with the tenant admin account.</span></span> <span data-ttu-id="7b30b-109">Azure 테넌트 관리자에게도 그룹 관리자 역할이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-109">The Azure tenant administrator should also have the Group administrator role.</span></span>

    ![그룹 관리자가 강조 표시](../media/lti-media/lti-group-admin.png)

2. <span data-ttu-id="7b30b-111">Microsoft OneDrive [LTI 포털에 로그인합니다.](https://odltiappnl.azurewebsites.net/admin)</span><span class="sxs-lookup"><span data-stu-id="7b30b-111">Sign in to the Microsoft [OneDrive LTI portal](https://odltiappnl.azurewebsites.net/admin).</span></span>

3. <span data-ttu-id="7b30b-112">로그인을 완료하려면 사용 권한을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-112">Accept the permissions to complete the sign-in.</span></span>

    ![사용 권한 수락](../media/lti-media/lti-permissions.png)

4. <span data-ttu-id="7b30b-114">LTI **테넌트 추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b30b-114">Select **Add LTI Tenant**.</span></span>

     ![LTI 테넌트 추가](../media/lti-media/lti-add-tenant.png)

5. <span data-ttu-id="7b30b-116">**드롭다운에서 LTI 소비자** 플랫폼을 **캔버스로** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-116">Select **LTI Consumer Platform** as **Canvas** from the dropdown.</span></span>

6. <span data-ttu-id="7b30b-117">캔버스 **기본 URL을 선택하고** 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b30b-117">Select **Canvas Base URL** and then select **Next**.</span></span>

    ![캔버스를 선택하고 기본 URL 추가](../media/lti-media/lti-canvas-base-url.png)

   <span data-ttu-id="7b30b-119">다음 화면에는 기밀 필드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-119">The next screen shows fields that are confidential to you.</span></span>

7. <span data-ttu-id="7b30b-120">**?에서 다음을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-120">Select **Next** from ??</span></span> <span data-ttu-id="7b30b-121">페이지.</span><span class="sxs-lookup"><span data-stu-id="7b30b-121">page.</span></span> <span data-ttu-id="7b30b-122">검토자는 여기에서 공백을 채울 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7b30b-122">CAN REVIEWERS FILL IN THE BLANK HERE?</span></span>

8. <span data-ttu-id="7b30b-123">**화면에서** 기밀 정보를 표시하는 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-123">Select **Next** in the screen that shows information that's confidential to you.</span></span>

   <span data-ttu-id="7b30b-124">Azure Portal의 마지막 화면에는 Canvas 인스턴스를 추가하기 위한 다음 단계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-124">The final screen of the Azure portal shows the next steps for adding your Canvas instance.</span></span>

9. <span data-ttu-id="7b30b-125">이 화면에서 개발자 키를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-125">Copy the Developer Keys from this screen.</span></span> <span data-ttu-id="7b30b-126">Canvas 인스턴스를 만들 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-126">You'll use when you create the Canvas instance.</span></span>

## <a name="add-the-canvas-instance"></a><span data-ttu-id="7b30b-127">Canvas 인스턴스 추가</span><span class="sxs-lookup"><span data-stu-id="7b30b-127">Add the Canvas instance</span></span>

1. <span data-ttu-id="7b30b-128">Canvas 인스턴스에서 관리자 개발자 **키의**  >  **선택을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b30b-128">In your Canvas instance, deselect **Admin** > **Developer Keys**.</span></span>

2. <span data-ttu-id="7b30b-129">개발자 **키의** 드롭다운에서 LTI **키를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="7b30b-129">Choose **LTI Key** in the dropdown on **Developer Key**.</span></span>

   ![LTI 개발자 키 얻기](../media/lti-media/lti-developer-keys.png)

3. <span data-ttu-id="7b30b-131">여기에 개발자 키를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-131">Paste the developer keys here.</span></span>

     ![개발자 키 붙여넣기](../media/lti-media/lti-developer-keys.png)

   <span data-ttu-id="7b30b-133">키가 **꺼진** 모드에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-133">The key gets created in **OFF** mode</span></span>

   ![오프 모드에서 생성된 개발자 키](../media/lti-media/lti-copy-developer-keys.png)

4. <span data-ttu-id="7b30b-135">강조 표시된 텍스트를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-135">Copy the highlighted text.</span></span>
    <span data-ttu-id="7b30b-136">이 ID는 LTI 포털에서 Microsoft OneDrive 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-136">This serves as Client ID in Microsoft OneDrive LTI portal.</span></span>

5. <span data-ttu-id="7b30b-137">LTI 포털의 클라이언트 **ID** 필드에 텍스트를 Microsoft OneDrive 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b30b-137">Paste the text into the **Client ID** field in Microsoft OneDrive LTI portal, and then select **Next**.</span></span>

6. <span data-ttu-id="7b30b-138">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b30b-138">Select **Save**.</span></span>

7. <span data-ttu-id="7b30b-139">LTI 테넌트 보기 를 선택하여 **설정을 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b30b-139">View the settings by selecting **View LTI Tenants**.</span></span>
