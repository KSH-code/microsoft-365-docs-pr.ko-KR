---
title: SharePoint Online 관리 센터에서 IRM(정보 권한 관리)을 설정
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Microsoft Azure RMS(Azure Active Directory Rights Management Services)를 통해 SharePoint Online IRM을 사용하여 SharePoint 목록 및 문서 라이브러리를 보호하는 방법을 설명합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919404"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a><span data-ttu-id="34f6b-103">SharePoint Online 관리 센터에서 IRM(정보 권한 관리)을 설정</span><span class="sxs-lookup"><span data-stu-id="34f6b-103">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>

<span data-ttu-id="34f6b-104">SharePoint Online에서 IRM 보호가 목록 및 라이브러리 수준의 파일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-104">Within SharePoint Online, IRM protection is applied to files at the list and library level.</span></span> <span data-ttu-id="34f6b-105">조직에서 IRM 보호를 사용하기 전에 먼저 권한 관리를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-105">Before your organization can use IRM protection, you must first set up Rights Management.</span></span> <span data-ttu-id="34f6b-106">IRM은 Microsoft Azure Information Protection의 Microsoft Azure AD Rights Management 서비스에 의존하여 사용 제한을 암호화하고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-106">IRM relies on the Azure Rights Management service from Azure Information Protection to encrypt and assign usage restrictions.</span></span> <span data-ttu-id="34f6b-107">일부 Microsoft 365 요금제에는 Azure 권한 관리가 포함되어 있지만 모든 계획이 포함되어 있지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-107">Some Microsoft 365 plans include Azure Rights Management, but not all.</span></span> <span data-ttu-id="34f6b-108">자세한 내용은 Office 응용 프로그램 및 [서비스에서 Azure Rights Management를 지원하는 방법을 읽어보아야 합니다.](/azure/information-protection/understand-explore/office-apps-services-support)</span><span class="sxs-lookup"><span data-stu-id="34f6b-108">To learn more, read [How Office applications and services support Azure Rights Management](/azure/information-protection/understand-explore/office-apps-services-support).</span></span>
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a><span data-ttu-id="34f6b-109">SharePoint 관리 센터를 사용하여 IRM 서비스 켜기</span><span class="sxs-lookup"><span data-stu-id="34f6b-109">Turn on IRM service using SharePoint admin center</span></span>

<span data-ttu-id="34f6b-110">조직에서 SharePoint 목록 및 라이브러리를 IRM으로 보호하려면 먼저 조직의 권한 관리 서비스를 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-110">Before your organization can IRM-protect SharePoint lists and libraries, you must first activate the Rights Management service for your organization.</span></span> <span data-ttu-id="34f6b-111">Azure 권한 관리 [활성화를 참조하세요.](/information-protection/deploy-use/activate-service)</span><span class="sxs-lookup"><span data-stu-id="34f6b-111">To learn how see [Activating Azure Rights Management](/information-protection/deploy-use/activate-service).</span></span> <span data-ttu-id="34f6b-112">전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 권한 관리 서비스를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-112">You must use a work or school account that has global administrator privileges to enable the Rights Management service.</span></span> <span data-ttu-id="34f6b-113">그렇지 않으면 SharePoint Online에서 IRM 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-113">Otherwise, you won't be able to use IRM features with SharePoint Online.</span></span>
  
<span data-ttu-id="34f6b-114">권한 관리 서비스를 활성화한 후 SharePoint 관리 센터에 로그인하여 IRM을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-114">After activating the Rights Management service, sign in to the SharePoint admin center to turn on IRM.</span></span>
  
1. <span data-ttu-id="34f6b-115">전역 관리자 또는 SharePoint 관리자로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-115">Sign in as a global admin or SharePoint admin.</span></span>
    
2. <span data-ttu-id="34f6b-116">왼쪽 위에서 앱 시작 관리자 아이콘 ![The app launcher icon in Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png)을 선택하고 **관리자** 를 선택하여 Microsoft 365 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-116">Select the app launcher icon ![The app launcher icon in Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in the upper-left and choose **Admin** to open the Microsoft 365 admin center.</span></span> <span data-ttu-id="34f6b-117">(관리 타일이 없는 경우 조직에 관리자 권한이 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="34f6b-117">(If you don't see the Admin tile, you don't have administrator permissions in your organization.)</span></span> 
    
3. <span data-ttu-id="34f6b-118">왼쪽 창에서 관리 **센터** \> **SharePoint 를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="34f6b-118">In the left pane, choose **Admin centers** \> **SharePoint**.</span></span>
    
4. <span data-ttu-id="34f6b-119">왼쪽 창에서 설정 을 선택한 다음 클래식 설정 **페이지를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="34f6b-119">In the left pane, choose **settings**, and then choose **classic settings page**.</span></span>
    
5. <span data-ttu-id="34f6b-120">**IRM(정보 권한 관리)** 섹션에서 구성에 지정된 **IRM** 서비스 사용을 선택한 다음 **새로 고침 IRM 설정 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="34f6b-120">In the **Information Rights Management (IRM)** section, choose **Use the IRM service specified in your configuration**, and then choose **Refresh IRM Settings**.</span></span> <span data-ttu-id="34f6b-121">IRM 설정을 새로 고치면 조직의 사용자들이 SharePoint 목록 및 문서 라이브러리에서 IRM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-121">After you refresh IRM settings, people in your organization can begin using IRM in their SharePoint lists and document libraries.</span></span> <span data-ttu-id="34f6b-122">그러나 라이브러리 설정 및 목록 설정에 표시하는 데 최대 1시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-122">However, the options to do so may take up to an hour to appear in Library Settings and List Settings.</span></span>
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a><span data-ttu-id="34f6b-123">SharePoint 문서 라이브러리 및 목록 IRM 사용</span><span class="sxs-lookup"><span data-stu-id="34f6b-123">IRM-enable SharePoint document libraries and lists</span></span>
<span data-ttu-id="34f6b-124"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="34f6b-124"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="34f6b-125">IRM 설정을 새로 고치면 사이트 소유자가 SharePoint 목록 및 문서 라이브러리를 IRM으로 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-125">After refreshing IRM settings, site owners can IRM-protect their SharePoint lists and document libraries.</span></span> <span data-ttu-id="34f6b-126">자세한 내용은 목록 또는 라이브러리에 정보 권한 관리 [적용을 참조하세요.](apply-irm-to-a-list-or-library.md)</span><span class="sxs-lookup"><span data-stu-id="34f6b-126">For more information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="34f6b-127">사이트 소유자가 목록 또는 라이브러리에 대해 IRM을 사용하도록 설정하면 해당 목록 또는 라이브러리에서 지원되는 모든 파일 형식을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-127">When site owners enable IRM for a list or library, they can protect any supported file types in that list or library.</span></span> <span data-ttu-id="34f6b-128">라이브러리에 IRM을 사용하도록 설정하면 권한 관리가 해당 라이브러리의 모든 파일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-128">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="34f6b-129">목록에 대해 IRM을 사용하도록 설정하면 실제 목록 항목이 아니라 목록 항목에 첨부된 파일에만 권한 관리가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-129">When you enable IRM for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="34f6b-130">사용자가 IRM 사용 목록 또는 라이브러리에서 파일을 다운로드하면 권한이 있는 사용자만 볼 수 있도록 파일이 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-130">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="34f6b-131">또한 각 권한 관리 파일에는 파일을 보는 사용자에 대한 제한을 적용하는 발행 라이선스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-131">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="34f6b-132">일반적인 제한 사항으로는 파일을 읽기 전용으로 설정하고, 텍스트 복사를 사용할 수 없습니다. 로컬 복사본을 저장하지 못하게 하며, 사용자가 파일을 인쇄할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-132">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="34f6b-133">IRM 지원 파일 형식을 읽을 수 있는 클라이언트 프로그램은 권한 관리 파일 내의 발행 라이선스를 사용하여 이러한 제한을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-133">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="34f6b-134">이는 권한 관리 파일이 다운로드된 후에도 보호를 유지하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-134">This is how a rights-managed file retains its protection even after it is downloaded.</span></span> <span data-ttu-id="34f6b-135">목록 또는 라이브러리에서 IRM을 사용하도록 설정하려면 목록 또는 라이브러리에 정보 권한 관리 [적용을 참조하세요.](apply-irm-to-a-list-or-library.md)</span><span class="sxs-lookup"><span data-stu-id="34f6b-135">To enable IRM on a list or library, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="34f6b-136">브라우저에서 Office를 사용하여 IRM 사용 라이브러리의 문서를 만들거나 편집할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-136">You cannot create or edit documents in an IRM-enabled library using Office in a browser.</span></span> <span data-ttu-id="34f6b-137">대신 한 번씩 한 사람이 IRM으로 암호화된 파일을 다운로드하고 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-137">Instead, one person at a time can download and edit IRM-encrypted files.</span></span> <span data-ttu-id="34f6b-138">체크 인 및 체크 아웃을 사용하여 여러 사용자에 대해 공동 작성  *또는*  제작을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-138">Use check-in and check-out to manage  *co-authoring*  , or authoring across multiple users.</span></span> 
  
<span data-ttu-id="34f6b-139">IRM으로 보호된 라이브러리에서 PDF 파일을 다운로드하면 Microsoft 365에서 보호된 PDF 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-139">When you download a PDF file from an IRM-protected library, Microsoft 365 creates a protected PDF file.</span></span> <span data-ttu-id="34f6b-140">파일의 확장명은 변경되지 않지만 파일이 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-140">The file's extension won't change, but the file is protected.</span></span> <span data-ttu-id="34f6b-141">이 파일을 보기 위해 Azure Information Protection 뷰어, 전체 Azure Information Protection 클라이언트 또는 보호된 PDF 파일 보기를 지원하는 다른 응용 프로그램이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-141">To view this file you'll need the Azure Information Protection viewer, the full Azure Information Protection client, or another application that supports viewing protected PDF files.</span></span> 
  
<span data-ttu-id="34f6b-142">SharePoint Online은 다음 파일 형식의 암호화를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-142">SharePoint Online supports encryption of the following file types:</span></span>
  
- <span data-ttu-id="34f6b-143">PDF</span><span class="sxs-lookup"><span data-stu-id="34f6b-143">PDF</span></span>
    
- <span data-ttu-id="34f6b-144">Word, Excel 및 PowerPoint와 같은 Microsoft Office 97-2003 파일 형식</span><span class="sxs-lookup"><span data-stu-id="34f6b-144">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="34f6b-145">Word, Excel 및 PowerPoint와 같은 Microsoft Office Office Open XML 형식</span><span class="sxs-lookup"><span data-stu-id="34f6b-145">The Office Open XML formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="34f6b-146">XPS(XML Paper Specification) 형식</span><span class="sxs-lookup"><span data-stu-id="34f6b-146">The XML Paper Specification (XPS) format</span></span>
 
> [!NOTE]
> <span data-ttu-id="34f6b-147">SharePoint에서 업로드 시 문서를 열기 위해 필요한 보호된 문서(예: 디지털 서명된 PDF 파일)에는 IRM 보호를 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-147">IRM protection cannot be applied to protected documents (like digitally signed PDF files) as SharePoint needs to open the document on upload.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="34f6b-148">다음 단계</span><span class="sxs-lookup"><span data-stu-id="34f6b-148">Next steps</span></span>
<span data-ttu-id="34f6b-149"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="34f6b-149"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="34f6b-150">SharePoint Online에 대해 IRM을 사용하도록 설정한 후 목록 및 라이브러리에 권한 관리 적용을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34f6b-150">Once you've enabled IRM for SharePoint Online, you can start applying rights management to lists and libraries.</span></span> <span data-ttu-id="34f6b-151">자세한 내용은 목록 또는 라이브러리에 정보 [권한 관리 적용을 참조하세요.](apply-irm-to-a-list-or-library.md)</span><span class="sxs-lookup"><span data-stu-id="34f6b-151">For information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="34f6b-152">Windows용 새 OneDrive 동기화 클라이언트는 이제 IRM으로 보호된 SharePoint 문서 라이브러리 및 OneDrive 위치 동기화를 지원합니다(라이브러리에 대한 IRM 설정이 문서 액세스 권한 만료로 설정되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="34f6b-152">The new OneDrive sync client for Windows now supports synchronizing IRM-protected SharePoint document libraries and OneDrive locations (as long as the IRM setting for the library isn't set to expire document access rights).</span></span> <span data-ttu-id="34f6b-153">자세한 내용은 새 동기화 클라이언트 배포를 시작하거나 [Windows용 새 OneDrive 동기화 클라이언트](/onedrive/deploy-on-windows)배포를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34f6b-153">For more information, or to get started deploying the new sync client, see [Deploy the new OneDrive sync client for Windows](/onedrive/deploy-on-windows).</span></span>
  
[<span data-ttu-id="34f6b-154">Top of page</span><span class="sxs-lookup"><span data-stu-id="34f6b-154">Top of page</span></span>](set-up-irm-in-sp-admin-center.md)