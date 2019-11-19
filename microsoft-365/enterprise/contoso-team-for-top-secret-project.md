---
title: Contoso Corporation의 최상위 비밀 프로젝트에 대 한 팀
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
description: '요약: Contoso가 상위 기밀 프로젝트에 대해 높은 규제 대상 데이터에 대 한 팀을 사용 하 여 새로운 제품 및 서비스 제품군을 개발 하는 방법을 설명 합니다.'
ms.openlocfilehash: 23a967ea7ffdb3497d705a3ddda4d3c56e415b8e
ms.sourcegitcommit: 0ceb79a633f7004e82b80e69b6f7a7329ccec7ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699906"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="49e82-103">Contoso Corporation의 최상위 비밀 프로젝트에 대 한 팀</span><span class="sxs-lookup"><span data-stu-id="49e82-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="49e82-104">경영진은이 Contoso의 CEO가 향후 5 년 동안 Contoso의 이익을 두 배로 만들 수 있는 새로운 제품 및 서비스 제품군의 개발을 주문 했습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="49e82-105">비즈니스, 엔지니어링 및 시장 계획을 개발 하기 위한 최상위 수준의 보안 프로젝트는 **프로젝트 2** , 회사 전체의 주요 직원 이라는 것이 recruited 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="49e82-106">연구 및 개발에 대 한 일정은 공동 작업을 효율적으로 수행 하 고 보안 모임, 진행 중인 대화 및 파일 저장을 제공 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="49e82-107">프로젝트 2의 결과 결과물은 비즈니스 계획, 제품 및 엔지니어링 사양, 마케팅 자료 및 일정은 Word, Excel 및 PowerPoint 파일 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="49e82-108">중요 한 특성으로 인해 다음과 같은 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="49e82-109">프로젝트 2 개 팀 구성원으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="49e82-110">DLP (데이터 손실 방지) 정책으로 보호 되어 프로젝트 2 팀 구성원이 팀 외부에서이를 공유 하지 못하도록 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="49e82-111">암호화 및 보호 된 파일은 Contoso 외부에 배포 된 경우에도 프로젝트 2 번째 팀 구성원 에게만 액세스를 허용 하는 사용 권한으로 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="49e82-112">Contoso IT 직원은 프로젝트에 대 한 [높은 규제 대상 데이터에 대 한 팀](secure-teams-highly-regulated-data-scenario.md) 을 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="49e82-113">1 단계: 개인 팀을 만들고 기본 SharePoint 사이트를 잠 궜 습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="49e82-114">팀의 기본 SharePoint 사이트에 대 한 액세스를 보호 하기 위해 Contoso IT 관리자는 [권장 되는 sharepoint 액세스 정책을](sharepoint-file-access-policies.md)구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="49e82-115">다음으로 Contoso IT 관리자가 Project 라는 새 비공개 팀을 만들고 프로젝트 2 개 직원의 사용자 계정을 구성원으로 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="49e82-116">다음으로, 프로젝트 2가 사이트에 대 한 액세스를 공유 하지 못하도록 하 고 사이트에 대 한 액세스 요청을 방지 하기 위해 사이트에 대 한 추가 사용 권한 설정을 구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="49e82-117">구성에 대 한 자세한 내용은 [고도로 규제 된 팀에 대 한 SharePoint 설정](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49e82-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="49e82-118">2 단계: 보존 레이블에 대 한 기본 사이트 및 DLP 정책 구성</span><span class="sxs-lookup"><span data-stu-id="49e82-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="49e82-119">첫째로, Contoso 관리자는 기존의 **고도로 기밀** Office 365 보존 레이블을 프로젝트의 기본 SharePoint 사이트 (팀)에 있는 **문서** 섹션에 적용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="49e82-120">다음으로, 다음은 **프로젝트 이름이 2** 인 새 OFFICE 365 DLP 정책을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-120">Next, they created a new Office 365 DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="49e82-121">높은 수준의 기밀 Office 365 보존 레이블을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-121">Uses the Highly Confidential Office 365 retention label.</span></span>
- <span data-ttu-id="49e82-122">사용자가 Contoso 외부의 팀 프로젝트에서 파일을 공유 하려고 할 때 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="49e82-123">구성에 대 한 자세한 내용은 [보존 레이블 및 DLP를 사용 하 여 팀의 파일 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49e82-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="49e82-124">3 단계: 프로젝트 2 팀에 대 한 Office 365 민감도 레이블 작성</span><span class="sxs-lookup"><span data-stu-id="49e82-124">Step 3: Created an Office 365 sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="49e82-125">Contoso 관리자는 다음과 같은 **Project가 2** 배인 새 Office 365 민감도 레이블을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-125">Contoso admins created a new Office 365 sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="49e82-126">암호화 필요</span><span class="sxs-lookup"><span data-stu-id="49e82-126">Requires encryption.</span></span>
- <span data-ttu-id="49e82-127">Office 365 그룹 2 개 프로젝트에 대해 공동 작성자 권한을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-127">Allows Co-Author permissions for the Project 2X Office 365 group.</span></span>

<span data-ttu-id="49e82-128">다음은 프로젝트를 2 배로 구성 하는 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-128">Here is the resulting configuration of the Project 2X team.</span></span>

![프로젝트 2 배의 결과 구성](./media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="49e82-130">원본으로 사용 하는 Project 2의 문서 섹션에 있는 파일은 다음과 같은 방법으로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="49e82-131">사이트 사용 권한-프로젝트 2 x 365 그룹 구성원 에게만 액세스를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-131">The site permissions, which only allow access to members of the Project 2X Office 365 group.</span></span>
- <span data-ttu-id="49e82-132">높은 기밀 보존 레이블-새 파일에 자동으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="49e82-133">고도로 기밀 보존 레이블과 파일을 외부 사용자와 공유 하지 못하도록 차단 하는 설정을 사용 하는 DLP 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="49e82-134">파일을 이동 하거나 복사 하는 경우 파일과 함께 이동 하는 암호화 및 사용 권한을 갖는 프로젝트 2X 민감도 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="49e82-135">다음은 원본으로 사용 되는 프로젝트에 저장 되는 파일의 예로, 높은 규제 대상 보존 레이블과 프로젝트 2X 민감도 레이블이 할당 되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![원본으로 사용 하는 프로젝트 2 개 사이트에 저장 된 파일의 예](./media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="49e82-137">4 단계: 팀 구성원 2 대 교육 프로젝트</span><span class="sxs-lookup"><span data-stu-id="49e82-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="49e82-138">Contoso 보안 직원은 다음과 같은 작업을 수행 하는 필수 과정을 통해 프로젝트를 2 배의 팀 구성원에 게 교육 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="49e82-139">새 프로젝트에 액세스 하는 방법 2 배, 모임 및 채팅을 사용 하 고 팀 파일을 공동으로 작업 하는 방법</span><span class="sxs-lookup"><span data-stu-id="49e82-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="49e82-140">팀에서 새 파일을 만들고 로컬로 만든 새 파일을 업로드 하는 방법</span><span class="sxs-lookup"><span data-stu-id="49e82-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="49e82-141">DLP 정책이 외부에서 파일을 공유 하지 못하도록 차단 하는 방법에 대 한 데모입니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="49e82-142">프로젝트의 민감도 레이블을 사용 하 여 파일에 레이블을 지정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="49e82-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="49e82-143">프로젝트가 팀에서 나간 경우에도 파일을 2 차원으로 보호 하는 방법을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="49e82-144">최종 결과는 프로젝트 2 개 팀 구성원이 대화방, 모임 및 파일을 위해 안전한 환경에서 collaborated 하는 보안 환경 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="49e82-145">두 개의 인스턴스에서 프로젝트 2 개 프로젝트의 보호 된 파일을 오프 라인 작업을 위해 로컬 드라이브로 다운로드 했습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="49e82-146">그러나 자격 증명을 열 때 확인 메시지가 표시 되 면 사용자가 실수로 메시지를 인식 하 고 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="49e82-147">팀의 공동 작업 환경 및 Microsoft 365의 보안 기능 때문에 프로젝트의 세부 정보는 프로젝트 기간 동안 기밀로 유지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="49e82-148">Contoso는 해당 계획을 발표 했으며, 고객 및 투자자의 안전 게 및 경쟁사의 chagrin에 새 제품 및 서비스를 배포 하는 프로세스를 진행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49e82-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="49e82-149">다음 단계</span><span class="sxs-lookup"><span data-stu-id="49e82-149">Next step</span></span>

<span data-ttu-id="49e82-150">[배포](deploy-microsoft-365-enterprise.md) 조직의 Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="49e82-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="49e82-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49e82-151">See also</span></span>

<span data-ttu-id="49e82-152">[Microsoft 365 생산성 라이브러리](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="49e82-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
