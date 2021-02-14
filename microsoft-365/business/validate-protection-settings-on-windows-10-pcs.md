---
title: Windows 10 PC에서 앱 보호 설정 유효성 검사
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Windows 10 장치에서 Microsoft 365 Business Premium 앱 보호 설정의 유효성을 검사하고 사용자가 회사 데이터를 개인 파일 또는 관리되지 않는 앱에 복사할 수 없는지 확인합니다.
ms.openlocfilehash: 589d2fc25cc1425a775523595881660cc03e152e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403393"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="ac899-103">Windows 10 PC에서 앱 보호 설정 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ac899-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="ac899-104">사용자가 회사 장치의 개인 파일에 회사 데이터를 복사할 수 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="ac899-105">앱 [보호](protection-settings-for-windows-10-devices.md)정책을 설정한 후 정책이 사용자의 장치에 적용되는 데 최대 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="ac899-106">사용자가 회사  데이터를 개인 파일에 복사하지 못하도록 설정하고 회사 소유 장치에 대한 비즈니스용 **OneDrive** 설정에 회사 파일을 저장하도록 강제로 설정한 경우 Azure AD에 연결하고 로그인한 후 사용자의 장치에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="ac899-107">**연결 설정 확인**</span><span class="sxs-lookup"><span data-stu-id="ac899-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="ac899-108">Microsoft 365 Business Premium 자격 증명으로 로그인하고 [Microsoft 365 Business Premium](set-up-windows-devices.md)사용자를 위한 Windows 장치 설정에 설명된 바와 같이 Azure AD에 연결한 후 Windows **설정** 계정 액세스 직장 또는 학교로 \>  \> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-108">After you sign in with Microsoft 365 Business Premium credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**.</span></span> <span data-ttu-id="ac899-109">**\<tenant name\> Azure AD에 연결 선택한** 다음 정보를 **선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="ac899-109">Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="ac899-111">관리되는 **페이지에서** 다음 그림과 같은 관리 서버 주소가 포함된 연결 정보를 볼 \<tenant name\> 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="ac899-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="ac899-113">**관리되지 않는 앱에 회사 데이터를 붙여넣을 수 없는지 확인**</span><span class="sxs-lookup"><span data-stu-id="ac899-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="ac899-114">Microsoft 365 Business Premium에서 설치한 Outlook 2016을 여는 경우</span><span class="sxs-lookup"><span data-stu-id="ac899-114">Open Outlook 2016 that was installed by Microsoft 365 Business Premium.</span></span>
    
2. <span data-ttu-id="ac899-115">전자 메일을 열고 전자 메일의 일부 콘텐츠를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="ac899-116">메모장을 열고 콘텐츠 붙여넣기를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="ac899-117">앱이 콘텐츠에 액세스할 수 없다고 표시하는 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="ac899-119">하지만 Word 2016에는 동일한 콘텐츠를 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="ac899-120">사용자가 개인 장치의 개인 파일에 회사 데이터를 복사할 수 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="ac899-121">**연결 설정 확인**</span><span class="sxs-lookup"><span data-stu-id="ac899-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="ac899-122">로컬 사용자로 로그인한 Windows 10 개인 장치에서 **Windows** 설정으로 이동한 다음 **계정** 액세스 직장 또는 학교를 클릭하거나 \> **탭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac899-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="ac899-123">**회사 또는 학교 액세스** 에서 **연결** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="ac899-124">직장 또는 학교 계정 설정 대화  상자 로그인에 Microsoft 365 Business Premium 자격 \> **증명을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac899-124">Enter your Microsoft 365 Business Premium credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="ac899-125">**회사 또는 학교 액세스** 페이지에서 **회사 또는 학교 계정** 을 선택한 다음 **정보** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![직장 또는 학교 계정 대화 상자에서 정보를 클릭하거나 탭합니다.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="ac899-127">Access 직장 **또는** 학교 페이지에서 다음  그림과 같은  관리 서버 주소를 포함하는 연결 정보를 볼 수 있으며 wip 및 *mam* 안에 *단어를* 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="ac899-129">**관리되지 않는 앱에 회사 데이터를 붙여넣을 수 없는지 확인**</span><span class="sxs-lookup"><span data-stu-id="ac899-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="ac899-130">Outlook 2016을 열고 필요한 경우 Microsoft 365 Business Premium 계정을 추가하고 Microsoft 365 Business Premium 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-130">Open Outlook 2016 and add your Microsoft 365 Business Premium account if necessary and sign in with your Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="ac899-131">전자 메일을 열고 전자 메일의 일부 콘텐츠를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="ac899-132">메모장을 열고 콘텐츠 붙여넣기를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="ac899-133">앱이 콘텐츠에 액세스할 수 없다고 표시하는 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="ac899-135">하지만 Word 2016에는 동일한 콘텐츠를 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac899-135">You can, however, paste the same content into Word 2016.</span></span>
    

