---
title: 목록 또는 라이브러리에 IRM(정보 권한 관리) 적용
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
- SPO_Content
description: IRM(정보 권한 관리)을 사용하여 목록 또는 라이브러리에서 다운로드한 파일을 제어하고 보호할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0648d511ee882765f1905e83ebdea673f306c186
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233354"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a><span data-ttu-id="3b867-103">목록 또는 라이브러리에 IRM(정보 권한 관리) 적용</span><span class="sxs-lookup"><span data-stu-id="3b867-103">Apply Information Rights Management (IRM) to a list or library</span></span>

<span data-ttu-id="3b867-104">IRM(정보 권한 관리)을 사용하여 목록 또는 라이브러리에서 다운로드한 파일을 제어하고 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-104">You can use Information Rights Management (IRM) to help control and protect files that are downloaded from lists or libraries.</span></span> <span data-ttu-id="3b867-105">이 기능은 Microsoft 전역 클라우드에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-105">This feature is only supported in the Microsoft global cloud.</span></span> <span data-ttu-id="3b867-106">국가 클라우드 배포의 목록 및 SharePoint 라이브러리에 대해 IRM이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-106">IRM is not supported for SharePoint lists and libraries in national cloud deployments.</span></span>
  
## <a name="administrator-preparations-before-applying-irm"></a><span data-ttu-id="3b867-107">IRM을 적용하기 전에 관리자 준비</span><span class="sxs-lookup"><span data-stu-id="3b867-107">Administrator preparations before applying IRM</span></span>

- <span data-ttu-id="3b867-108">Azure Information Protection의 Azure RMS(Azure 권한 관리 서비스) 및 AD RMS(Active Directory Rights Management Services)에서 사이트에 대한 정보 권한 관리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-108">The Azure Rights Management service (Azure RMS) from Azure Information Protection, and the on-premises equivalent, Active Directory Rights Management Services (AD RMS), support Information Rights Management for sites.</span></span> <span data-ttu-id="3b867-109">별도의 설치나 추가 설치는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-109">No separate or additional installations are required.</span></span>

- <span data-ttu-id="3b867-110">목록 또는 라이브러리에 IRM을 적용하기 전에 사이트에 대해 IRM을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-110">Before you apply IRM to a list or library, you need to enable IRM for your site.</span></span> <span data-ttu-id="3b867-111">IRM을 사용하도록 설정하려면 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-111">You'll need administrator permissions to enable IRM.</span></span>

- <span data-ttu-id="3b867-112">목록 또는 라이브러리에 IRM을 적용하려면 해당 목록 또는 라이브러리에 대한 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-112">To apply IRM to a list or library, you must have administrator permissions for that list or library.</span></span>

- <span data-ttu-id="3b867-113">SharePoint Online을 사용하는 경우 IRM으로 보호된 더 큰 파일을 다운로드할 때 시간이 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-113">If you're using SharePoint Online, your users might experience timeouts when downloading larger IRM-protected files.</span></span> <span data-ttu-id="3b867-114">시간 제한을 방지하려면 Office 프로그램을 사용하여 IRM 보호를 적용하고 더 큰 파일을 IRM을 사용하지 않는 SharePoint 라이브러리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-114">To avoid timeouts, use your Office programs to apply IRM protection, and store larger files in a SharePoint library that doesn't use IRM.</span></span>

> [!NOTE]
> <span data-ttu-id="3b867-115">SharePoint Server 2013을 사용하는 경우 서버 관리자는 조직의 사용자가 IRM을 사용하여 보호하려는 모든 파일 형식에 대해 모든 프런트 엔드 웹 서버에 보호 기능을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-115">If you're using SharePoint Server 2013, a server administrator must install protectors on all front-end Web servers for every file type that the people in your organization want to protect by using IRM.</span></span>
  
## <a name="apply-irm-to-a-list-or-library"></a><span data-ttu-id="3b867-116">목록 또는 라이브러리에 IRM 적용</span><span class="sxs-lookup"><span data-stu-id="3b867-116">Apply IRM to a list or library</span></span>
<span data-ttu-id="3b867-117"><a name="__toc256598179"> </a></span><span class="sxs-lookup"><span data-stu-id="3b867-117"><a name="__toc256598179"> </a></span></span>

![정보 권한 관리 설정](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. <span data-ttu-id="3b867-119">IRM을 구성할 목록 또는 라이브러리로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b867-119">Go to the list or library for which you want to configure IRM.</span></span>

2. <span data-ttu-id="3b867-120">리본 메뉴에서 라이브러리 탭을 **선택한** 다음 라이브러리 탭을 **설정.**</span><span class="sxs-lookup"><span data-stu-id="3b867-120">On the ribbon, select the **Library** tab, and then select **Library Settings**.</span></span> <span data-ttu-id="3b867-121">(목록에서 작업하는 경우 목록 탭을 선택한 다음 목록 탭을 **설정).** </span><span class="sxs-lookup"><span data-stu-id="3b867-121">(If you're working in a list, select the **List** tab, and then select **List Settings**).</span></span>
    
    ![SharePoint 리본의 설정 단추](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. <span data-ttu-id="3b867-123">사용 **권한 및 관리에서** **정보 권한 관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3b867-123">Under **Permissions and Management**, select **Information Rights Management**.</span></span> <span data-ttu-id="3b867-124">정보 권한 관리 링크가 나타나지 않는 경우 사이트에 대해 IRM을 사용하도록 설정하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-124">If the Information Rights Management link doesn't appear, IRM might not be enabled for your site.</span></span> <span data-ttu-id="3b867-125">서버 관리자에게 문의하여 사이트에 대해 IRM을 사용하도록 설정할 수 있는지 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b867-125">Contact your server administrator to see if you can enable IRM for your site.</span></span> <span data-ttu-id="3b867-126">그림 **라이브러리에는** 정보 권한 관리 링크가 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-126">The **Information Rights Management** link doesn't appear for picture libraries.</span></span>

4. <span data-ttu-id="3b867-127">정보 **권한** 관리 설정 페이지에서 다운로드 시  이 라이브러리의 문서에 대한 사용 권한 제한 확인란을 선택하여 사용자가 이 목록 또는 라이브러리에서 다운로드하는 문서에 대해 제한된 사용 권한을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-127">On the **Information Rights Management Settings** page, select the **Restrict permission to documents in this library on download** check box to apply restricted permission to documents users download from this list or library.</span></span>

5. <span data-ttu-id="3b867-128">권한 **정책 만들기 제목** 상자에 정책에 대한 설명이 있는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-128">In the **Create a permission policy title** box, enter a descriptive name for the policy.</span></span> <span data-ttu-id="3b867-129">다른 정책에서 이 정책을 식별하는 데 도움이 되는 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-129">Use a name that helps you identify this policy from other policies.</span></span> <span data-ttu-id="3b867-130">예를 들어 **회사** 기밀을 사용하여 기밀 회사 문서가 포함된 목록 또는 라이브러리에 제한된 사용 권한을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-130">For example, use **Company Confidential** to apply restricted permissions to a list or library that contains confidential company documents.</span></span>

6. <span data-ttu-id="3b867-131">권한 **정책** 설명 추가 상자에 이 목록 또는 라이브러리를 사용하는 사용자가 이 목록 또는 라이브러리의 문서를 처리하는 방법을 설명하는 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-131">In the **Add a permission policy description** box, type a description that will appear to people who use this list or library that explains how they should handle the documents in this list or library.</span></span> <span data-ttu-id="3b867-132">예를 들어 문서의  정보에 대한 액세스를 내부 직원으로 제한하려는 경우 이 문서의 내용을 다른 직원과만 논의를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-132">For example, you can type **Discuss the contents of this document only with other employees** if you want to restrict access to the information in these documents to internal employees.</span></span> 

7. <span data-ttu-id="3b867-133">이 목록 또는 라이브러리의 문서에 추가 제한을 적용하려면 옵션 표시 를 선택하고 다음 중 원하는 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-133">To apply additional restrictions to the documents in this list or library, select **Show Options**, and do any of the following:</span></span>

|<span data-ttu-id="3b867-134">**이렇게 하려면 다음을 수행합니다.**</span><span class="sxs-lookup"><span data-stu-id="3b867-134">**To do this:**</span></span>|<span data-ttu-id="3b867-135">**이렇게 할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="3b867-135">**Do this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3b867-136">사용자가 이 목록 또는 라이브러리에서 문서를 인쇄하도록 허용</span><span class="sxs-lookup"><span data-stu-id="3b867-136">Allow people to print documents from this list or library</span></span>|<span data-ttu-id="3b867-137">**뷰어가 인쇄할 수 있도록 허용 확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-137">Select the **Allow viewers to print** check box.</span></span>|
|<span data-ttu-id="3b867-138">적어도 항목 보기 권한이 있는 사용자가 문서에 포함된 코드나 매크로를 실행할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-138">Allow people with at least the View Items permission to run embedded code or macros on a document.</span></span>|<span data-ttu-id="3b867-139">뷰어가 스크립트 및 화면 읽기 프로그램을 실행하여 다운로드한 문서에서 작동하도록 **허용 확인란을** 선택합니다. 이 옵션을 선택하면 사용자가 코드를 실행하여 문서의 내용을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-139">Select the **Allow viewers to run script and screen reader to function on downloaded documents** check box.If you select this option, users could run code to extract the contents of a document.</span></span>           |
|<span data-ttu-id="3b867-140">콘텐츠에 대한 액세스를 지정된 기간으로 제한하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-140">Select this option if you want to restrict access to content to a specified period of time.</span></span> <span data-ttu-id="3b867-141">이 옵션을 선택하면 콘텐츠에 액세스하기 위한 사용자의 발행 라이선스가 지정된 일 수 후에 만료되고, 자격 증명을 확인하고 새 복사본을 다운로드하기 위해 서버로 돌아와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-141">If you select this option, people's issuance licenses to access the content will expire after the specified number of days, and people will be required to return to the server to verify their credentials and download a new copy.</span></span>|<span data-ttu-id="3b867-142">다운로드 후 문서 액세스 권한은 이 일 **수(1-365)** 후에 만료됩니다. 확인란을 선택한 다음 문서를 볼 수 있도록 할 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-142">Select the **After download, document access rights will expire after these number of days (1-365)** check box, and then specify the number of days for which you want the document to be viewable.</span></span>|
| <span data-ttu-id="3b867-143">IRM을 지원하지 않는 문서를 이 목록 또는 라이브러리에 업로드하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-143">Prevent people from uploading documents that do not support IRM to this list or library.</span></span> <span data-ttu-id="3b867-144">이 옵션을 선택하면 모든 프런트 엔드 웹 서버에 해당하는 IRM 보호기 설치가 없는 파일 형식의 파일 형식을 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-144">If you select this option, people will not be able to upload any of the following file types: File types that do not have corresponding IRM protectors installed on all of the front-end web servers.</span></span> <span data-ttu-id="3b867-145">Server 2010에서 SharePoint 파일 형식의 암호를 해독할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-145">File types that SharePoint Server 2010 cannot decrypt.</span></span> <span data-ttu-id="3b867-146">다른 프로그램에서 IRM으로 보호되는 파일 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-146">File types that are IRM protected in another program.</span></span>|<span data-ttu-id="3b867-147">사용자가 **IRM을 지원하지 않는** 문서를 업로드할 수 있도록 허용 안 함 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-147">Select the **Do not allow users to upload documents that do not support IRM** check box.</span></span>|
|<span data-ttu-id="3b867-148">특정 날짜에 이 목록 또는 라이브러리에서 제한된 사용 권한을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-148">Remove restricted permissions from this list or library on a specific date.</span></span>|<span data-ttu-id="3b867-149">에서 **라이브러리에** 대한 액세스 제한 중지 확인란을 선택한 다음 원하는 날짜를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-149">Select the **Stop restricting access to the library at** check box, and then select the date that you want.</span></span>|
|<span data-ttu-id="3b867-150">문서를 열 수 있는 사용이 허가된 프로그램에 대해 자격 증명이 캐시되는 간격을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-150">Control the interval that credentials are cached for the program that is licensed to open the document.</span></span>|<span data-ttu-id="3b867-151">사용자가  이 간격(일) 확인란을 사용하여 자격 증명을 확인해야 합니다. 확인란을 선택한 다음 자격 증명을 캐싱할 간격을 일 수로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-151">Select the **Users must verify their credentials using this interval (days)** check box, then enter the interval for caching credentials in number of days.</span></span>|
|<span data-ttu-id="3b867-152">사용자가 같은 그룹의 구성원과 공유할 수 있도록 그룹 보호를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-152">Allow group protection so that users can share with members of the same group.</span></span>|<span data-ttu-id="3b867-153">그룹 **보호 허용을 선택하고** 공유를 위해 그룹의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-153">Select **Allow group protection**, and enter the group's name for sharing.</span></span>|

8. <span data-ttu-id="3b867-154">원하는 옵션 선택을 마친 후 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="3b867-154">After you finish selecting the options you want, select **OK**.</span></span>
  
## <a name="what-is-information-rights-management"></a><span data-ttu-id="3b867-155">정보 권한 관리란?</span><span class="sxs-lookup"><span data-stu-id="3b867-155">What is Information Rights Management?</span></span>
<span data-ttu-id="3b867-156"><a name="__toc256598175"> </a></span><span class="sxs-lookup"><span data-stu-id="3b867-156"><a name="__toc256598175"> </a></span></span>

<span data-ttu-id="3b867-157">IRM(정보 권한 관리)을 사용하면 목록 또는 라이브러리에서 다운로드한 파일에 대해 사용자가 수행할 수 있는 작업을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-157">Information Rights Management (IRM) enables you to limit the actions that users can take on files that have been downloaded from lists or libraries.</span></span> <span data-ttu-id="3b867-158">IRM은 다운로드한 파일을 암호화하고 이러한 파일의 암호를 해독할 수 있는 사용자 및 프로그램 집합을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-158">IRM encrypts the downloaded files and limits the set of users and programs that are allowed to decrypt these files.</span></span> <span data-ttu-id="3b867-159">또한 IRM은 파일 읽기가 허용되는 사용자의 권한도 제한하여 사용자가 파일 복사본 인쇄, 파일의 텍스트 복사와 같은 작업을 수행할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-159">IRM can also limit the rights of the users who are allowed to read files, so that they cannot take actions such as print copies of the files or copy text from them.</span></span>
  
<span data-ttu-id="3b867-160">목록 또는 라이브러리에서 IRM을 사용하여 중요한 콘텐츠의 배포를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-160">You can use IRM on lists or libraries to limit the dissemination of sensitive content.</span></span> <span data-ttu-id="3b867-161">예를 들어 예정된 제품에 대한 정보를 선택한 마케팅 담당자와 공유하기 위해 문서 라이브러리를 만드는 경우 IRM을 사용하여 이러한 개인이 회사의 다른 직원과 이 콘텐츠를 공유하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-161">For example, if you are creating a document library to share information about upcoming products with selected marketing representatives, you can use IRM to prevent these individuals from sharing this content with other employees in the company.</span></span>
  
<span data-ttu-id="3b867-162">사이트에서는 개별 파일이 아닌 전체 목록 또는 라이브러리에 IRM을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-162">On a site, you apply IRM to an entire list or library, rather than to individual files.</span></span> <span data-ttu-id="3b867-163">따라서 전체 문서 또는 파일 집합에 대한 일관된 보호 수준을 보다 쉽게 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-163">This makes it easier to ensure a consistent level of protection for an entire set of documents or files.</span></span> <span data-ttu-id="3b867-164">따라서 IRM은 조직에서 기밀 또는 독점 정보의 사용 및 보급을 규정하는 회사 정책을 적용하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-164">IRM can thus help your organization to enforce corporate policies that govern the use and dissemination of confidential or proprietary information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b867-165">정보 권한 관리에 관한 이 페이지의 정보는 Microsoft SharePoint Server 2013 및 SharePoint Server 2016 사용권 계약에서 '정보 권한 관리'를 참조하는 모든 용어를 대신합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-165">The information on this page regarding Information Rights Management supersedes any terms that reference 'Information Rights Management' in any Microsoft SharePoint Server 2013 and SharePoint Server 2016 license term agreements.</span></span> 
  
### <a name="how-irm-can-help-protect-content"></a><span data-ttu-id="3b867-166">IRM이 콘텐츠를 보호하는 데 도움이 되는 방법</span><span class="sxs-lookup"><span data-stu-id="3b867-166">How IRM can help protect content</span></span>
<span data-ttu-id="3b867-167"><a name="__toc256598176"> </a></span><span class="sxs-lookup"><span data-stu-id="3b867-167"><a name="__toc256598176"> </a></span></span>

<span data-ttu-id="3b867-168">IRM은 다음과 같은 방법으로 제한된 콘텐츠를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-168">IRM helps to protect restricted content in the following ways:</span></span>
  
- <span data-ttu-id="3b867-169">권한이 부여된 뷰어가 무단으로 사용하기 위해 콘텐츠를 복사, 수정, 인쇄, 팩스 또는 복사 및 붙여넣는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-169">Helps to prevent an authorized viewer from copying, modifying, printing, faxing, or copying and pasting the content for unauthorized use</span></span>
    
- <span data-ttu-id="3b867-170">Microsoft 365의 인쇄 화면 기능을 사용하여 권한이 부여된 뷰어가 콘텐츠를 복사하지 못하게 Windows</span><span class="sxs-lookup"><span data-stu-id="3b867-170">Helps to prevent an authorized viewer from copying the content by using the Print Screen feature in Microsoft Windows</span></span>
    
- <span data-ttu-id="3b867-171">권한이 없는 뷰어가 서버에서 다운로드한 후 전자 메일로 전송되는 경우 콘텐츠를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-171">Helps to prevent an unauthorized viewer from viewing the content if it is sent in e-mail after it is downloaded from the server</span></span>
    
- <span data-ttu-id="3b867-172">지정된 기간 동안 콘텐츠에 대한 액세스를 제한합니다. 이후에 사용자가 자격 증명을 확인하고 콘텐츠를 다시 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-172">Restricts access to content to a specified period of time, after which users must confirm their credentials and download the content again</span></span>
    
- <span data-ttu-id="3b867-173">조직 내에서 콘텐츠의 사용 및 보용을 규제하는 회사 정책을 적용하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-173">Helps to enforce corporate policies that govern the use and dissemination of content within your organization</span></span>
    
### <a name="how-irm-cannot-help-protect-content"></a><span data-ttu-id="3b867-174">IRM으로 콘텐츠를 보호할 수 없는 방법</span><span class="sxs-lookup"><span data-stu-id="3b867-174">How IRM cannot help protect content</span></span>
<span data-ttu-id="3b867-175"><a name="__toc256598177"> </a></span><span class="sxs-lookup"><span data-stu-id="3b867-175"><a name="__toc256598177"> </a></span></span>

<span data-ttu-id="3b867-176">IRM은 다음으로부터 제한된 콘텐츠를 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-176">IRM cannot protect restricted content from the following:</span></span>
  
- <span data-ttu-id="3b867-177">트로이 목마, 키 입력 로거 및 특정 유형의 스파이웨어와 같은 악성 프로그램에 의해 삭제, 도난, 캡처 또는 전송</span><span class="sxs-lookup"><span data-stu-id="3b867-177">Erasure, theft, capture, or transmission by malicious programs such as Trojan horses, keystroke loggers, and certain types of spyware</span></span>
    
- <span data-ttu-id="3b867-178">컴퓨터 바이러스의 작업으로 인해 손실 또는 손상</span><span class="sxs-lookup"><span data-stu-id="3b867-178">Loss or corruption because of the actions of computer viruses</span></span>
    
- <span data-ttu-id="3b867-179">화면의 디스플레이에서 콘텐츠 수동 복사 또는 다시 타이핑</span><span class="sxs-lookup"><span data-stu-id="3b867-179">Manual copying or retyping of content from the display on a screen</span></span>
    
- <span data-ttu-id="3b867-180">화면에 표시되는 콘텐츠의 디지털 또는 영화 사진</span><span class="sxs-lookup"><span data-stu-id="3b867-180">Digital or film photography of content that is displayed on a screen</span></span>
    
- <span data-ttu-id="3b867-181">타사 화면 캡처 프로그램을 사용하여 복사</span><span class="sxs-lookup"><span data-stu-id="3b867-181">Copying through the use of third-party screen-capture programs</span></span>
    
- <span data-ttu-id="3b867-182">타사 화면 캡처 프로그램 또는 복사 및 붙여넣기 작업을 통해 콘텐츠 메타데이터(열 값) 복사</span><span class="sxs-lookup"><span data-stu-id="3b867-182">Copying of content metadata (column values) through the use of third-party screen-capture programs or copy-and-paste action</span></span>
  
## <a name="how-irm-works-for-lists-and-libraries"></a><span data-ttu-id="3b867-183">목록 및 라이브러리에 대해 IRM이 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="3b867-183">How IRM works for lists and libraries</span></span>
<span data-ttu-id="3b867-184"><a name="__toc256598178"> </a></span><span class="sxs-lookup"><span data-stu-id="3b867-184"><a name="__toc256598178"> </a></span></span>

<span data-ttu-id="3b867-185">IRM 보호는 목록 또는 라이브러리 수준의 파일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-185">IRM protection is applied to files at the list or library level.</span></span> <span data-ttu-id="3b867-186">라이브러리에 IRM을 사용하도록 설정하면 권한 관리가 해당 라이브러리의 모든 파일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-186">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="3b867-187">목록에 IRM을 사용하도록 설정하면 권한 관리가 실제 목록 항목이 아닌 목록 항목에 첨부된 파일에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-187">When IRM is enabled for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="3b867-188">사용자가 IRM 사용 목록 또는 라이브러리에서 파일을 다운로드하면 권한이 있는 사용자만 볼 수 있도록 파일이 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-188">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="3b867-189">또한 각 권한 관리 파일에는 파일을 보는 사용자에 대한 제한을 적용하는 발행 라이선스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-189">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="3b867-190">일반적인 제한 사항으로는 파일을 읽기 전용으로 설정하고, 텍스트 복사를 사용할 수 없습니다. 로컬 복사본을 저장하지 못하게 하며, 사용자가 파일을 인쇄할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-190">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="3b867-191">IRM 지원 파일 형식을 읽을 수 있는 클라이언트 프로그램은 권한 관리 파일 내의 발행 라이선스를 사용하여 이러한 제한을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-191">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="3b867-192">이는 권한 관리 파일이 서버에서 다운로드된 후에도 보호를 유지하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-192">This is how a rights-managed file retains its protection even after it is downloaded from the server.</span></span>
  
<span data-ttu-id="3b867-193">목록 또는 라이브러리에서 파일을 다운로드할 때 파일에 적용되는 제한 유형은 파일이 포함된 사이트에 대한 개별 사용자의 사용 권한을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-193">The types of restrictions that are applied to a file when it is downloaded from a list or library are based on the individual user's permissions on the site that contains the file.</span></span> <span data-ttu-id="3b867-194">다음 표에서는 사이트에 대한 사용 권한이 IRM 사용 권한에 해당하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-194">The following table explains how the permissions on sites correspond to IRM permissions.</span></span>
  
|<span data-ttu-id="3b867-195">**사용 권한**</span><span class="sxs-lookup"><span data-stu-id="3b867-195">**Permissions**</span></span>|<span data-ttu-id="3b867-196">**IRM 사용 권한**</span><span class="sxs-lookup"><span data-stu-id="3b867-196">**IRM Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3b867-197">사용 권한 관리, 웹 사이트 관리</span><span class="sxs-lookup"><span data-stu-id="3b867-197">Manage Permissions, Manage Web Site</span></span>|<span data-ttu-id="3b867-198">**클라이언트 프로그램에서** 정의한 모든 권한: 이 권한은 일반적으로 사용자가 권한 관리 콘텐츠의 사용 권한을 읽고, 편집, 복사, 저장하고, 수정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-198">**Full control** (as defined by the client program): This permission generally allows a user to read, edit, copy, save, and modify permissions of rights-managed content.</span></span>|
|<span data-ttu-id="3b867-199">항목 편집, 목록 관리, 페이지 추가 및 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="3b867-199">Edit Items, Manage Lists, Add and Customize Pages</span></span>|<span data-ttu-id="3b867-200">**편집,** **복사** 및 **저장:** 사용자가 목록 또는  라이브러리의 정보 권한 관리 설정 페이지에서 사용자가 문서를 인쇄하도록 허용 확인란을 선택한 경우만 파일을 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-200">**Edit**, **Copy**, and **Save**: A user can print a file only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>|
|<span data-ttu-id="3b867-201">항목 보기</span><span class="sxs-lookup"><span data-stu-id="3b867-201">View Items</span></span>|<span data-ttu-id="3b867-202">**읽기:** 사용자가 문서를 읽을 수는 있지만 콘텐츠를 복사하거나 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-202">**Read**: A user can read the document, but cannot copy or modify its content.</span></span> <span data-ttu-id="3b867-203">사용자가 목록 또는 라이브러리의 정보 권한 관리 설정 문서 인쇄 허용 확인란을 선택한 설정 인쇄할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="3b867-203">A user can print only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>|
|<span data-ttu-id="3b867-204">기타</span><span class="sxs-lookup"><span data-stu-id="3b867-204">Other</span></span>|<span data-ttu-id="3b867-205">다른 사용 권한은 IRM 사용 권한에 직접 해당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-205">No other permissions correspond directly to IRM permissions.</span></span>|
   
<span data-ttu-id="3b867-206">SharePoint Server 2013에서 목록 또는 라이브러리에 대해 IRM을 사용하도록 설정하면 보호가 모든 프런트 엔드 웹 서버에 설치된 해당 목록 또는 라이브러리의 파일 형식만 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-206">When you enable IRM for a list or library in SharePoint Server 2013, you can only protect file types in that list or library for which a protector is installed on all front-end web servers.</span></span> <span data-ttu-id="3b867-207">보호기 는 특정 파일 형식의 권한 관리 파일의 암호화 및 암호 해독을 제어하는 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-207">A protector is a program that controls the encryption and decryption of rights-managed files of a specific file format.</span></span> <span data-ttu-id="3b867-208">SharePoint 파일 형식에 대한 보호가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-208">SharePoint includes protectors for the following file types:</span></span>
  
- <span data-ttu-id="3b867-209">Microsoft Office InfoPath 양식</span><span class="sxs-lookup"><span data-stu-id="3b867-209">Microsoft Office InfoPath forms</span></span>
    
- <span data-ttu-id="3b867-210">Word, Excel 및 Microsoft Office 프로그램용 97-2003 파일 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="3b867-210">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="3b867-211">Word, Office 및 Microsoft Office 프로그램용 Open XML Excel 형식을 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="3b867-211">The Office Open XML Formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="3b867-212">XPS(XML Paper Specification) 형식</span><span class="sxs-lookup"><span data-stu-id="3b867-212">The XML Paper Specification (XPS) format</span></span>
    
<span data-ttu-id="3b867-213">조직에서 위에 나열된 파일 형식 외에도 IRM을 사용하여 다른 파일 형식을 보호하려면 서버 관리자가 이러한 추가 파일 형식에 대한 보호 기능을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b867-213">If your organization plans to use IRM to protect any other file types in addition to those listed above, your server administrator must install protectors for these additional file formats.</span></span>
  

