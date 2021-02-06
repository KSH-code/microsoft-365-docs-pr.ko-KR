---
title: 준수 관리자용 Microsoft 준수 구성 분석기
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 준수 구성 분석기를 사용하여 Microsoft 준수 관리자를 사용하여 빠르게 시작하고 실행하는 방법을 이해합니다.
ms.openlocfilehash: 86c4b04deb8313f3013a6d9ad349c0f4112db773
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122398"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="206fd-103">준수 관리자용 Microsoft 준수 구성 분석기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="206fd-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="206fd-104">**이 문서에서:** Microsoft 준수 관리자를 빠르게 시작할 수 있도록 Microsoft 규정 준수 구성 분석기 도구를 설치 및 실행하는 방법을 알아보고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="206fd-105">MCCA(Microsoft 준수 구성 분석기)(미리 보기) 개요</span><span class="sxs-lookup"><span data-stu-id="206fd-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="206fd-106">MCCA(Microsoft 준수 구성 분석기)는 Microsoft 준수 관리자를 시작하는 데 도움이 되는 미리 보기 [도구입니다.](compliance-manager.md)</span><span class="sxs-lookup"><span data-stu-id="206fd-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="206fd-107">MCCA는 조직의 현재 구성을 반기하고 Microsoft 365 권장 모범 사례에 대해 유효성을 검사하는 PowerShell 기반 유틸리티입니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="206fd-108">이러한 모범 사례는 데이터 보호 및 데이터 거버넌스에 대한 주요 규정 및 표준을 포함 하는 컨트롤 집합을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="206fd-109">MCCA를 사용하면 준수 관리의 개선 작업이 현재 Microsoft 365 환경에 적용되는지 빠르게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="206fd-110">MCCA로 식별된 각 작업은 준수 관리자 및 해당 솔루션에 대한 직접 링크가 있는 구현에 대한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="206fd-111">MCCA를 이해하기 위한 추가 리소스는 [GitHub의 README 지침을 방문하는 것입니다.](https://github.com/OfficeDev/MCCA#overview)</span><span class="sxs-lookup"><span data-stu-id="206fd-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="206fd-112">이 페이지에서는 선행 구성에 대한 자세한 정보를 제공하며 전체 설치 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="206fd-113">이 페이지에 액세스하는 데 GitHub 계정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="206fd-114">**가용성**: MCCA는 Office 365 및 Microsoft 365 라이선스 및 GCC(미국 정부 커뮤니티) 보통 고객을 통해 모든 조직에서 사용할 수 있으며 GCC High 고객에게 서비스를 확장하기 위해 계획이 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate customers, with plans underway to expand service to to GCC High customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="206fd-115">MCCA 설치 및 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="206fd-115">Install MCCA and run a report</span></span>

<span data-ttu-id="206fd-116">MCCA 도구를 설치하려면 다음을 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="206fd-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="206fd-117">도구를 다운로드하여 설치한 후 보고서를 실행하기 위해 이러한 단계를 반복할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="206fd-118">MCCA를 열 때마다 로그인 자격 증명을 묻고 업데이트된 새 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="206fd-119">1단계: 설치 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="206fd-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="206fd-120">시작하려면 PowerShell 갤러리에서 사용할 수 있는 Exchange Online PowerShell 모듈(v2.0.3 이상)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="206fd-121">[설치 지침을 얻습니다.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)</span><span class="sxs-lookup"><span data-stu-id="206fd-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="206fd-122">2단계: MCCA 설치</span><span class="sxs-lookup"><span data-stu-id="206fd-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="206fd-123">MCCA를 설치하려면 관리자 모드에서 PowerShell을 사용하여 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="206fd-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="206fd-124">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-124">Follow the steps below:</span></span>

1. <span data-ttu-id="206fd-125">Windows 시작 **단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="206fd-126">**PowerShell을 입력하고** 마우스 오른쪽 단추로 Windows PowerShell 관리자 **권한으로 실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="206fd-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="206fd-127">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="206fd-128">3단계: 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="206fd-128">Step 3: Run a report</span></span>

<span data-ttu-id="206fd-129">MCCA를 설치한 후 MCCA를 실행하고 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="206fd-130">보고서를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-130">To run a report:</span></span>

1. <span data-ttu-id="206fd-131">PowerShell 열기</span><span class="sxs-lookup"><span data-stu-id="206fd-131">Open PowerShell</span></span>
2. <span data-ttu-id="206fd-132">cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```
3. <span data-ttu-id="206fd-133">MCCA가 실행된 후 초기 버전 확인을 통해 자격 증명을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-133">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="206fd-134">사용자 이름 입력 프롬프트에서 Microsoft 365 계정 전자 메일 주소로 로그인합니다(보고서를 만들 수 있는 역할[보기).](#role-based-reporting)</span><span class="sxs-lookup"><span data-stu-id="206fd-134">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="206fd-135">그런 다음 암호 프롬프트에 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-135">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="206fd-136">그러면 보고서를 생성하는 데 약 2~5분이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-136">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="206fd-137">완료되면 브라우저 창이 열리며 HTML 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-137">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="206fd-138">도구를 실행할 때마다 자격 증명을 요청하고 새 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-138">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="206fd-139">이 보고서는 다음 디렉터리에 로컬로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-139">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="206fd-140">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="206fd-140">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="206fd-141">이 디렉터리에서 이전에 생성된 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-141">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="206fd-142">보고서 이해</span><span class="sxs-lookup"><span data-stu-id="206fd-142">Understanding your report</span></span>

<span data-ttu-id="206fd-143">보고서에는 보고서가 생성된 날짜와 시간을 기준으로 데이터가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-143">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="206fd-144">맨 위 섹션에서는 생성된 경우, 조직 이름 및 테넌트 ID에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-144">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="206fd-145">지리적 위치 기반 보고</span><span class="sxs-lookup"><span data-stu-id="206fd-145">Geolocation-based reporting</span></span>

<span data-ttu-id="206fd-146">참고 **섹션에는** 테넌트의 지리적 위치에 따라 보고서가 사용자 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-146">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="206fd-147">도구에 나열된 권장 사항은 해당 국가 또는 지역에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-147">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="206fd-148">지리적 위치 선택은 해당 지리적 위치와 관련된 중요한 정보 유형(SITS)을 평가하고 국가 또는 지역에 맞게 보고서를 생성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-148">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="206fd-149">테넌트에 있는 데이터에 따라 지리적 위치 선택</span><span class="sxs-lookup"><span data-stu-id="206fd-149">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="206fd-150">보고서의 위치 정보를 변경하려면 지리적 위치(-Geo) 입력 매개 변수를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-150">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="206fd-151">테넌트에 적용할 수 있는 지리적 위치 중 하나 또는 여러 개를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-151">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="206fd-152">다음 지침에 따라 특정 위치에 따라 보고서를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-152">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="206fd-153">PowerShell 열기</span><span class="sxs-lookup"><span data-stu-id="206fd-153">Open PowerShell</span></span>
2. <span data-ttu-id="206fd-154">특정 지역을 지정하기 위해 아래 표의 숫자를 사용하여 국가 또는 지역에 해당하는 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-154">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="206fd-155">숫자를 여러 개 입력할 때 각 번호를 콤보로 구분하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-155">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="206fd-156">예를 들어 아래 cmdlet은 사용자 지정 보고서를 Asia-Pacific 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-156">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="206fd-157">입력</span><span class="sxs-lookup"><span data-stu-id="206fd-157">Input</span></span> |  <span data-ttu-id="206fd-158">국가 또는 지역</span><span class="sxs-lookup"><span data-stu-id="206fd-158">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="206fd-159">1 </span><span class="sxs-lookup"><span data-stu-id="206fd-159">1</span></span> | <span data-ttu-id="206fd-160">아시아 태평양</span><span class="sxs-lookup"><span data-stu-id="206fd-160">Asia-Pacific</span></span> |
  | <span data-ttu-id="206fd-161">2 </span><span class="sxs-lookup"><span data-stu-id="206fd-161">2</span></span> | <span data-ttu-id="206fd-162">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="206fd-162">Australia</span></span> |
  | <span data-ttu-id="206fd-163">3 </span><span class="sxs-lookup"><span data-stu-id="206fd-163">3</span></span> | <span data-ttu-id="206fd-164">캐나다</span><span class="sxs-lookup"><span data-stu-id="206fd-164">Canada</span></span> |
  | <span data-ttu-id="206fd-165">4 </span><span class="sxs-lookup"><span data-stu-id="206fd-165">4</span></span> | <span data-ttu-id="206fd-166">유럽(프랑스 제외) /중동/아프리카</span><span class="sxs-lookup"><span data-stu-id="206fd-166">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="206fd-167">5 </span><span class="sxs-lookup"><span data-stu-id="206fd-167">5</span></span> | <span data-ttu-id="206fd-168">프랑스</span><span class="sxs-lookup"><span data-stu-id="206fd-168">France</span></span> |
  | <span data-ttu-id="206fd-169">6 </span><span class="sxs-lookup"><span data-stu-id="206fd-169">6</span></span> | <span data-ttu-id="206fd-170">인도</span><span class="sxs-lookup"><span data-stu-id="206fd-170">India</span></span> |
  | <span data-ttu-id="206fd-171">7 </span><span class="sxs-lookup"><span data-stu-id="206fd-171">7</span></span> | <span data-ttu-id="206fd-172">일본</span><span class="sxs-lookup"><span data-stu-id="206fd-172">Japan</span></span> |
  | <span data-ttu-id="206fd-173">8 </span><span class="sxs-lookup"><span data-stu-id="206fd-173">8</span></span> | <span data-ttu-id="206fd-174">한국</span><span class="sxs-lookup"><span data-stu-id="206fd-174">Korea</span></span> |
  | <span data-ttu-id="206fd-175">9 </span><span class="sxs-lookup"><span data-stu-id="206fd-175">9</span></span> | <span data-ttu-id="206fd-176">북미(캐나다 제외)</span><span class="sxs-lookup"><span data-stu-id="206fd-176">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="206fd-177">10 </span><span class="sxs-lookup"><span data-stu-id="206fd-177">10</span></span> | <span data-ttu-id="206fd-178">남미</span><span class="sxs-lookup"><span data-stu-id="206fd-178">South America</span></span> |
  | <span data-ttu-id="206fd-179">11 </span><span class="sxs-lookup"><span data-stu-id="206fd-179">11</span></span> | <span data-ttu-id="206fd-180">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="206fd-180">South Africa</span></span> |
  | <span data-ttu-id="206fd-181">12 </span><span class="sxs-lookup"><span data-stu-id="206fd-181">12</span></span> | <span data-ttu-id="206fd-182">스위스</span><span class="sxs-lookup"><span data-stu-id="206fd-182">Switzerland</span></span> |
  | <span data-ttu-id="206fd-183">13 </span><span class="sxs-lookup"><span data-stu-id="206fd-183">13</span></span> | <span data-ttu-id="206fd-184">아랍에미리트</span><span class="sxs-lookup"><span data-stu-id="206fd-184">United Arab Emirates</span></span> |
  | <span data-ttu-id="206fd-185">14 </span><span class="sxs-lookup"><span data-stu-id="206fd-185">14</span></span> | <span data-ttu-id="206fd-186">영국</span><span class="sxs-lookup"><span data-stu-id="206fd-186">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="206fd-187">보고서에는 항상 MCCA에서 지원되는 SWIFT 코드, 신용 카드 번호 등의 국제 중요한 정보 유형이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-187">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="206fd-188">역할 기반 보고</span><span class="sxs-lookup"><span data-stu-id="206fd-188">Role-based reporting</span></span>

<span data-ttu-id="206fd-189">또한 역할에 따라 보고서가 사용자 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-189">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="206fd-190">아래 표에는 보고서의 어떤 섹션에 액세스할 수 있는 역할이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-190">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="206fd-191">아래 표에 나열되지 않은 조직 내의 다른 역할은 도구를 실행하지 못하거나 도구를 실행하여 최종 보고서의 정보에 제한적으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-191">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="206fd-192">![MCCA - 역할](../media/compliance-manager-mcca-roles.png "MCCA 역할")</span><span class="sxs-lookup"><span data-stu-id="206fd-192">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="206fd-193">예외:</span><span class="sxs-lookup"><span data-stu-id="206fd-193">Exceptions:</span></span>
1. <span data-ttu-id="206fd-194">사용자는 "Exchange Online에 IRM 사용" 섹션과 별도로 IP에 대한 보고서를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-194">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="206fd-195">사용자는 "Exchange Online에 IRM 사용" 섹션과 별도로 IP에 대한 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-195">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="206fd-196">사용자는 "O365에서 통신 준수 사용" 섹션과 별도로 IP에 대한 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-196">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="206fd-197">사용자는 "Office 365에서 감사 사용" 섹션과 별도로 IP에 대한 보고서를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-197">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="206fd-198">사용자는 "Office 365에서 감사 사용" 섹션과 별도로 IP에 대한 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-198">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="206fd-199">솔루션 요약 섹션</span><span class="sxs-lookup"><span data-stu-id="206fd-199">Solutions Summary section</span></span>

<span data-ttu-id="206fd-200">보고서의 **솔루션 요약** 섹션에서는 준수 관리자에서 조직이 준수 자세를 개선하는 데 도움이 될 수 있는 개선 작업에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-200">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="206fd-201">![MCCA - 솔루션 요약](../media/compliance-manager-mcca-solutions.png "MCCA 솔루션 요약 화면")</span><span class="sxs-lookup"><span data-stu-id="206fd-201">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="206fd-202">MCCA는 준수 관리자에서 권장되는 개선 작업에 대해 현재 구성을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-202">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="206fd-203">주의가 필요한 것으로 MCCA 도구로 식별된 모든 개선 작업이 이 섹션에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-203">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="206fd-204">각 Microsoft 솔루션 옆에는 준수 관리자의 개선 작업에 해당하는 항목 수를 나타내는 색으로 코딩된 상자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-204">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="206fd-205">작업은 다음 세 가지 상태로 나됩니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-205">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="206fd-206">**확인**: 권장 조건을 충족하고 현재 주의가 필요 없는 작업</span><span class="sxs-lookup"><span data-stu-id="206fd-206">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="206fd-207">**개선** 사항 : 주의가 필요한 작업</span><span class="sxs-lookup"><span data-stu-id="206fd-207">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="206fd-208">**권장 사항:** 주의할 필요는 없지만 모범 사례를 권장하는 작업</span><span class="sxs-lookup"><span data-stu-id="206fd-208">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="206fd-209">개선 사항 및 권장 사항을 확인하려면 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-209">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="206fd-210">**개선 상태가 있는 항목**</span><span class="sxs-lookup"><span data-stu-id="206fd-210">**Items with the Improvement status**</span></span>

<span data-ttu-id="206fd-211">개선 작업 오른쪽에  있는 개선 레이블 옆에 있는 드롭다운을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-211">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="206fd-212">현재 설정 및 권장되는 개선 작업에 대한 빠른 요약 및 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-212">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="206fd-213">요약에는 준수 관리자에 대한 직접 링크, Microsoft 365 규정 준수 센터의 해당 솔루션 및 관련 설명서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-213">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="206fd-214">준수 관리자 링크를 클릭하면 아직 구현하지 않은 해당 솔루션 내의 모든 개선 작업을 필터링된 보기로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-214">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="206fd-215">이 지점에서 준수 점수를 높이기 위해 달성할 [](compliance-score-calculation.md)수 있는 포인트 수와 적용된 평가, 적용 가능한 규정 및 인증을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-215">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="206fd-216">DLP의 경우 권장되는  작업을 기반으로 미리 생성된 PowerShell 스크립트를 제공하는 수정 스크립트 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-216">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="206fd-217">PowerShell 콘솔에서 직접 복사하여 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-217">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="206fd-218">테스트 모드에서 DLP 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-218">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="206fd-219">**추천 상태가 있는 항목**</span><span class="sxs-lookup"><span data-stu-id="206fd-219">**Items with Recommendation status**</span></span>

<span data-ttu-id="206fd-220">개선 작업 오른쪽에  있는 추천 레이블 옆에 있는 드롭다운을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-220">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="206fd-221">개선 작업과 관련된 조직의 현재 Microsoft 365 환경에 대한 요약과 권장 모범 사례가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="206fd-221">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="206fd-222">리소스</span><span class="sxs-lookup"><span data-stu-id="206fd-222">Resources</span></span>

<span data-ttu-id="206fd-223">MCCA 설치, 설정 및 사용에 대한 자세한 내용은 [GitHub의 README](https://github.com/OfficeDev/MCCA#overview) 지침을 참조하세요(GitHub 계정 필요 없음).</span><span class="sxs-lookup"><span data-stu-id="206fd-223">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="206fd-224">자세한 내용은 Windows PowerShell PowerShell 설명서를 사용하는 [방법부터 시작하세요.](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="206fd-224">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="206fd-225">자세한 내용은 [시작 Windows PowerShell.](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="206fd-225">See also [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
