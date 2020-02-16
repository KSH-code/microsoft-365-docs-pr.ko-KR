---
title: Contoso Corporation의 고도로 기밀 디지털 자산에 대 한 SharePoint 사이트
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: '요약: Contoso가 높은 규제 대상 데이터에 대 한 SharePoint 사이트를 구현 하 여 조사 팀 간의 공동 작업을 간편 하 게 수행 하는 방법'
ms.openlocfilehash: a1ffb336e85eb6eb850b53ed14adf947b56642cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068280"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="913f4-103">Contoso Corporation의 고도로 기밀 디지털 자산에 대 한 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="913f4-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

<span data-ttu-id="913f4-104">Contoso의 가장 귀중 한 자산은 특허 제조 기술 및 개발 중인 제품에 대 한 디자인 사양과 같은 영업 비밀의 형태로 지적 재산입니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-104">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="913f4-105">이러한 자산은 디지털 형식으로, 원래는 SharePoint Server 2016 사이트에 파일로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-105">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="913f4-106">Contoso는 Microsoft 365 Enterprise를 배포한 경우 파리, 모스크바, 뉴욕, 베이징 및 Bangalore의 조사 팀에서 보다 쉽게 액세스 하 고 공동 작업을 수행할 수 있도록 온-프레미스 디지털 자산을 클라우드로 전환 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-106">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="913f4-107">그러나 중요 한 특성으로 인해 이러한 파일에 대 한 액세스는 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-107">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="913f4-108">액세스를 허용 하는 사용자 집합으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-108">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="913f4-109">사용자가 사이트 외부에 분산 되지 못하도록 DLP (데이터 손실 방지) 정책으로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-109">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="913f4-110">암호화 및 보호 권한 없는 사용자가 사이트 외부에 배포 된 경우에도 해당 콘텐츠에 액세스 하지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="913f4-110">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="913f4-111">Contoso의 IT 부서에서 보안 및 SharePoint 관리자는 [높은 규제 대상 데이터에 대 한 sharepoint 사이트](teams-sharepoint-online-sites-highly-regulated-data.md)를 사용 하기로 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-111">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="913f4-112">Contoso는 이러한 단계를 사용 하 여 연구 팀에 대 한 SharePoint 팀 사이트를 만들고 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-112">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="913f4-113">1 단계: 개인 SharePoint 팀 사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="913f4-113">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="913f4-114">SharePoint 사이트에 대 한 액세스를 보호 하기 위해 Contoso IT IT는 [권장 되는 sharepoint 액세스 정책을](sharepoint-file-access-policies.md)구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-114">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="913f4-115">다음으로, Contoso IT admins는 파리, 모스크바, 뉴욕, 베이징 및 Bangalore 사무소의 연구원에 대 한 사용자 계정 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-115">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="913f4-116">다음으로 Contoso IT 관리자가 **Research** 라는 새 개인 팀 사이트를 만들고 해당 연구원에 대 한 모든 사용자 계정을 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-116">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="913f4-117">그런 다음 사이트에 대 한 액세스를 공유 하 고 연구원 들이 사이트에 대 한 액세스를 요청 하는 것을 방지 하기 위해 사이트에 대 한 추가 사용 권한 설정을 구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-117">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="913f4-118">2 단계: 제한적인 DLP 정책에 맞게 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="913f4-118">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="913f4-119">먼저, Contoso admins가 기존 **고도로 기밀** Office 365 보존 레이블을 **리서치** 사이트의 문서 폴더에 적용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="913f4-120">다음으로, 다음은 **Research** 라는 새 OFFICE 365 DLP 정책을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-120">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="913f4-121">**높은 수준의 기밀** Office 365 보존 레이블을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-121">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="913f4-122">사용자가 Contoso 외부의 **리서치** 사이트에서 디지털 자산을 공유 하려고 할 때 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-122">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="913f4-123">구성에 대 한 자세한 내용은 [보존 레이블 및 DLP를 사용 하 여 SharePoint 파일 보호](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="913f4-123">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="913f4-124">3 단계: 사이트에 대 한 Office 365 민감도 sublabel를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-124">Step 3: Created an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="913f4-125">Contoso 관리자는 다음과 같은 **고도로 기밀** 레이블의 **리서치 팀** 이라는 새 Office 365 민감도 sublabel를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-125">Contoso admins created a new Office 365 sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="913f4-126">암호화 필요</span><span class="sxs-lookup"><span data-stu-id="913f4-126">Requires encryption.</span></span>
- <span data-ttu-id="913f4-127">**리서치** Office 365 그룹에 대해 공동 작성자 권한을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-127">Allows Co-Author permissions for the **Research** Office 365 group</span></span>
- <span data-ttu-id="913f4-128">**리서치** Office 365 그룹에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-128">Applies to the **Research** Office 365 group</span></span>

<span data-ttu-id="913f4-129">높은 기밀 자산에 대 한 **연구** 팀 사이트의 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-129">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![높은 기밀 자산에 대 한 연구 팀 사이트의 결과 구성](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="913f4-131">**리서치** 사이트의 폴더에 있는 파일은 다음과 같은 방법으로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-131">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="913f4-132">사이트 사용 권한- **리서치** Office 365 그룹의 구성원 에게만 액세스를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-132">The site permissions, which only allow access to members of the **Research** Office 365 group.</span></span>
- <span data-ttu-id="913f4-133">**고급 기밀** 보존 레이블과 파일을 외부 사용자와 공유 하지 않도록 하는 설정을 사용 하는 **연구** DLP 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-133">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="913f4-134">리서치 **팀** 에서 **리서치** 사이트를 이동 하거나 복사 하는 경우 해당 파일과 함께 이동 하는 암호화 및 사용 권한을 포함 하는 sublabel의 민감도를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-134">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="913f4-135">다음은 **리서치 사이트에** 저장 되어 있는 **리서치 팀** 민감도 sublabel 지정 된 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-135">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![높은 기밀 자산에 대 한 연구 팀 사이트의 결과 구성](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="913f4-137">4 단계: 온-프레미스 SharePoint 조사 데이터 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="913f4-137">Step 4: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="913f4-138">Contoso 관리자가 온-프레미스 SharePoint Server 2016 사이트의 모든 온-프레미스 조사 파일을 새 **리서치** SharePoint 사이트의 폴더로 이동 했습니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-138">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-5-trained-their-researchers"></a><span data-ttu-id="913f4-139">5 단계: 교육을 받은 연구원</span><span class="sxs-lookup"><span data-stu-id="913f4-139">Step 5: Trained their researchers</span></span>

<span data-ttu-id="913f4-140">Contoso 보안 직원은 **리서치** Office 365 그룹의 구성원을 단계별로 진행 하는 필수 과정으로 교육 합니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-140">Contoso security staff trained the members of the **Research** Office 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="913f4-141">새 **리서치** 사이트 및 기존 파일에 액세스 하는 방법</span><span class="sxs-lookup"><span data-stu-id="913f4-141">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="913f4-142">사이트에서 새 파일을 만들고 로컬에 저장된 새 파일을 업로드하는 방법</span><span class="sxs-lookup"><span data-stu-id="913f4-142">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="913f4-143">**연구** DLP 정책이 파일을 외부적으로 공유 하지 못하도록 차단 하는 방법에 대 한 데모입니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-143">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="913f4-144">**리서치 팀** 민감도 sublabel을 사용 하 여 파일에 레이블을 지정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="913f4-144">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="913f4-145">**리서치 팀** 하위 레이블이 사이트에서 누설 된 경우에도 파일을 보호 하는 방법을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-145">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="913f4-146">최종 결과는 리서치 정보가 포함 된 파일에 대 한 보안 환경에서 Contoso를 통해 공동 작업을 수행할 수 있는 보안 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-146">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="913f4-147">리서치 **팀** 이 포함 된 리서치 문서를 sublabel 하 게 되 면 유효한 사용자 계정 자격 증명을 사용 하 여 **리서치** Office 365 그룹의 구성원만 **이 사이트를** 암호화 하 고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="913f4-147">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Office 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="913f4-148">다음 단계</span><span class="sxs-lookup"><span data-stu-id="913f4-148">Next step</span></span>

<span data-ttu-id="913f4-149">[배포](deploy-microsoft-365-enterprise.md) 조직의 Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="913f4-149">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="913f4-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="913f4-150">See also</span></span>

<span data-ttu-id="913f4-151">[Microsoft 365 생산성 라이브러리](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="913f4-151">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
