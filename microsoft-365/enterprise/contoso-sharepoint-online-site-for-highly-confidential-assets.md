---
title: Contoso Corporation의 고도로 기밀 디지털 자산을 위한 SharePoint Online 사이트
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: '요약: Contoso가 높은 규제 대상 데이터에 대 한 SharePoint Online 사이트를 구현 하 여 조사 팀 간의 공동 작업을 보다 쉽게 수행할 수 있도록 합니다.'
ms.openlocfilehash: 99599829658e5dc46c8adebfe59f5c6d09b165de
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072786"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="21936-103">Contoso Corporation의 고도로 기밀 디지털 자산을 위한 SharePoint Online 사이트</span><span class="sxs-lookup"><span data-stu-id="21936-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="21936-104">**요약:** Contoso에서 높은 규제 대상 데이터에 대 한 SharePoint Online 사이트를 구현 하 여 조사 팀 간의 공동 작업을 보다 쉽게 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="21936-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="21936-105">Contoso의 가장 귀중 한 자산은 특허 제조 기술 및 개발 중인 제품에 대 한 디자인 사양과 같은 영업 비밀의 형태로 지적 재산입니다.</span><span class="sxs-lookup"><span data-stu-id="21936-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="21936-106">이러한 자산은 디지털 형식으로, 원래는 SharePoint Server 2016 사이트에 파일로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21936-106">These assets are in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="21936-107">Contoso는 Microsoft 365 Enterprise를 배포한 경우 파리, 모스크바, 뉴욕, 베이징 및 Bangalore의 조사 팀에서 보다 쉽게 액세스 하 고 공동 작업을 수행할 수 있도록 온-프레미스 디지털 자산을 클라우드로 전환 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="21936-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="21936-108">그러나 중요 한 특성으로 인해 이러한 파일에 대 한 액세스는 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21936-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="21936-109">SharePoint 관리자만 관리 하는 사이트에 대 한 지속적인 사용 권한을 사용 하 여 보거나 변경할 수 있는 사용자 집합으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21936-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="21936-110">사용자가 사이트 외부로 배포 하지 못하도록 DLP (데이터 손실 방지)로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21936-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="21936-111">암호화 및 보호 된 액세스 제어 목록을 사용 하 여 권한 없는 사용자가 사이트 외부에서 배포 된 경우에도 콘텐츠에 액세스할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="21936-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="21936-112">Contoso의 IT 부서에서 보안 및 SharePoint 관리자는 [높은 규제 대상 데이터에 대 한 Sharepoint Online 사이트](teams-sharepoint-online-sites-highly-regulated-data.md)를 사용 하기로 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="21936-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="21936-113">Contoso는 이러한 단계를 사용 하 여 연구 팀을 위한 SharePoint Online 팀 사이트를 만들고 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="21936-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="21936-114">1 단계: 연구 팀 그룹의 구성원을 검토 하 고 확인 함</span><span class="sxs-lookup"><span data-stu-id="21936-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="21936-115">Contoso IT 관리자는 리서치 팀에 대 한 보안 그룹 집합을 검토 했습니다.</span><span class="sxs-lookup"><span data-stu-id="21936-115">Contoso IT admins performed a review of the set of security groups for their research teams.</span></span> <span data-ttu-id="21936-116">사용자가 연구원을 선택 하지 않았거나 자산을 조사 하기 위해 액세스 하지 않아도 되는 사람은 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="21936-116">They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="21936-117">또한 다음과 같은 새 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="21936-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="21936-118">**관리자**  사용 권한 수정 기능을 포함 하 여 사이트에 대 한 모든 권한을 가지는 SharePoint 관리자 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="21936-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="21936-119">**리서치-구성원**  전 세계의 연구 팀에 대 한 보안 그룹 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="21936-119">**Research-Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="21936-120">**리서치-뷰어**  리서치 조직의 임원 같은 사이트의 자산을 볼 수만 있는 관리 사용자 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="21936-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can only view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="21936-121">2 단계: 격리 된 SharePoint Online 팀 사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="21936-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="21936-122">Contoso SharePoint 관리자가 먼저 **Research**라는 새 팀 사이트를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="21936-122">Contoso SharePoint admins first created a new team site named **Research**.</span></span> <span data-ttu-id="21936-123">그런 다음 다음을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="21936-123">They then configured:</span></span>

- <span data-ttu-id="21936-124">**관리자 수준의** 보안 그룹을 구성원으로 갖는 리서치 소유자 SharePoint 그룹을 사용 하기 위한 모든 권한 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="21936-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="21936-125">**리서치** 구성원 보안 그룹을 구성원으로 가진 리서치 구성원 SharePoint 그룹을 사용 하기 위한 편집 권한 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="21936-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="21936-126">**리서치** 방문자 보안 그룹을 구성원으로 포함 하는 리서치 방문객 SharePoint 그룹을 사용할 수 있는 읽기 권한 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="21936-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="21936-127">다음은 SharePoint 사용 권한 수준, SharePoint 그룹 및 해당 구성원에 대 한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="21936-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="21936-128">다음으로, 사이트에 대 한 추가 제한을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="21936-128">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="21936-129">구성에 대 한 자세한 내용은 [격리 된 SharePoint Online 팀 사이트 배포](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21936-129">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="21936-130">3 단계: 제한적인 DLP 정책에 맞게 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="21936-130">Step 3: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="21936-131">첫째로, Contoso 관리자는 **리서치** 사이트에 **고도로 기밀** Office 365 보존 레이블을 적용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="21936-131">First, Contoso admins applied the **Highly Confidential** Office 365 retention label to the **Research** site.</span></span>

<span data-ttu-id="21936-132">다음으로, 다음은 **Research** 라는 새 OFFICE 365 DLP 정책을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="21936-132">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="21936-133">**높은 수준의 기밀** Office 365 보존 레이블을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21936-133">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="21936-134">**리서치** 사이트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21936-134">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="21936-135">사용자가 Contoso 외부의 **리서치** 사이트에서 디지털 자산을 공유 하려고 할 때 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="21936-135">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="21936-136">구성에 대 한 자세한 내용은 [보존 레이블 및 DLP를 사용 하 여 SharePoint Online 파일 보호](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21936-136">For the configuration details, see [Protect SharePoint Online files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="21936-137">4 단계: 사이트에 대 한 Azure Information Protection 하위 레이블 만들기</span><span class="sxs-lookup"><span data-stu-id="21936-137">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="21936-138">Contoso 관리자는 다음과 같은 범위가 지정 된 정책에서 기본 **고도로 기밀** 레이블 **Research** 라는 새로운 Azure Information Protection 하위 레이블을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="21936-138">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="21936-139">암호화 필요</span><span class="sxs-lookup"><span data-stu-id="21936-139">Requires encryption.</span></span>
- <span data-ttu-id="21936-140">**연구-구성원** 보안 그룹 구성원의 모든 권한을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21936-140">Allows full access by members of the **Research-Members** security group.</span></span>
- <span data-ttu-id="21936-141">**리서치-뷰어** 보안 그룹의 구성원에 게 읽기 액세스를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21936-141">Allows read access by members of the **Research-Viewers** security group.</span></span>

<span data-ttu-id="21936-142">다음으로, Azure Information Protection 클라이언트를 연구 팀 구성원의 장치에 배포 했습니다.</span><span class="sxs-lookup"><span data-stu-id="21936-142">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="21936-143">구성에 대 한 자세한 내용은 [Azure Information Protection을 사용 하 여 SharePoint Online 파일 보호](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21936-143">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="21936-144">높은 기밀 자산에 대 한 **리서치** 사이트의 결과 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21936-144">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="21936-145">**리서치** 사이트의 폴더에 있는 파일은 다음과 같은 방법으로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21936-145">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="21936-146">리서치 \*\*\*\* Azure Information Protection Sublabel- **리서치** 사이트에서 이동 하거나 복사할 때 파일과 함께 이동 하는 각 파일에 암호화 및 permssions를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21936-146">The **Research** Azure Information Protection sublabel, which applies encryption and permssions to each file that travel with the file when it is moved or copied from the **Research** site.</span></span>
- <span data-ttu-id="21936-147">**중요 한** 보존 레이블과 파일을 외부 사용자와 공유 하지 않도록 하는 설정을 사용 하는 **연구** DLP 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="21936-147">The **Research** DLP policy, which uses the **Highly Sensitive** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="21936-148">리서치- **구성원** 및 연구 보안 그룹의 구성원에 대 한 액세스를 허용 하는 사이트 \*\*\*\* 권한 집합을 사용 하 고,이를 관리 하 \*\*\*\* 는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21936-148">The set of site permissions, which only allow access to members of the **Research-Members** and **Research-Viewers** security groups and administration by members of the **Research-Admins** security group.</span></span>

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="21936-149">5 단계: 온-프레미스 SharePoint 조사 데이터 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="21936-149">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="21936-150">Contoso 관리자가 온-프레미스 SharePoint Server 2016 사이트의 모든 온-프레미스 조사 파일을 새 **리서치** SharePoint Online 사이트의 폴더로 이동 했습니다.</span><span class="sxs-lookup"><span data-stu-id="21936-150">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="21936-151">6 단계: 사용자 교육</span><span class="sxs-lookup"><span data-stu-id="21936-151">Step 6: Trained their users</span></span> 

<span data-ttu-id="21936-152">Contoso 보안 직원은 조사 팀을 단계별로 진행 하는 필수 과정을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="21936-152">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="21936-153">새 **리서치** SharePoint Online 사이트 및 기존 파일에 액세스 하는 방법</span><span class="sxs-lookup"><span data-stu-id="21936-153">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="21936-154">사이트에서 새 파일을 만들고 로컬에 저장된 새 파일을 업로드하는 방법</span><span class="sxs-lookup"><span data-stu-id="21936-154">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="21936-155">DLP 정책이 외부에서 파일을 공유 하지 못하도록 차단 하는 방법에 대 한 데모입니다.</span><span class="sxs-lookup"><span data-stu-id="21936-155">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="21936-156">Azure Information Protection 클라이언트를 사용 하 여 리서치 하위 레이블로 조사 파일에 \*\*\*\* 레이블을 지정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="21936-156">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="21936-157">**리서치** 하위 레이블이 사이트에서 누설 된 경우에도 파일을 보호 하는 방법을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="21936-157">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="21936-158">최종 결과는 보안 환경에서 조직 전체에서 공동 작업을 수행할 수 있는 안전한 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="21936-158">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="21936-159">리서치 하위 레이블이 포함 된 조사 \*\*\*\* 문서가 **리서치** 사이트에서 누설 되는 경우에는 암호화 되 고 유효한 자격 증명을 가진 리서치- **검토자** 보안 그룹의 구성원 에게만 액세스 가능 합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="21936-159">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research-Members** and **Research-Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="21936-160">다음 단계</span><span class="sxs-lookup"><span data-stu-id="21936-160">Next step</span></span>

<span data-ttu-id="21936-161">[배포](deploy-microsoft-365-enterprise.md) 조직의 Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="21936-161">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

