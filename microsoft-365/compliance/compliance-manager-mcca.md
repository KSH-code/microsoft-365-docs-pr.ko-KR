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
ms.openlocfilehash: a77f38dcc0c0215e539c868e47135f5d7194f4b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906040"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="974da-103">준수 관리자용 Microsoft 준수 구성 분석기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="974da-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="974da-104">**이 문서의 예는** Microsoft 준수 관리자를 빠르게 시작할 수 있도록 Microsoft 준수 구성 분석기 도구를 설치하고 실행하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="974da-105">MCCA(Microsoft 준수 구성 분석기)(미리 보기) 개요</span><span class="sxs-lookup"><span data-stu-id="974da-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="974da-106">MCCA(Microsoft 준수 구성 분석기)는 Microsoft 준수 관리자를 시작하는 데 도움이 되는 미리 보기 [도구입니다.](compliance-manager.md)</span><span class="sxs-lookup"><span data-stu-id="974da-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="974da-107">MCCA는 조직의 현재 구성을 반기하고 Microsoft 365 권장 모범 사례에 대해 유효성을 검사하는 PowerShell 기반 유틸리티입니다.</span><span class="sxs-lookup"><span data-stu-id="974da-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="974da-108">이러한 모범 사례는 데이터 보호 및 데이터 거버넌스에 대한 주요 규정 및 표준을 포함 하는 제어 집합을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="974da-109">MCCA를 사용하면 규정 준수 관리의 개선 작업을 현재 Microsoft 365 환경에 빠르게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="974da-110">MCCA로 식별된 각 작업은 준수 관리자에 대한 직접 링크 및 해당 솔루션에 대한 구현에 대한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="974da-111">MCCA를 이해하기 위한 추가 리소스는 [GitHub의 README 지침을 방문하는 것입니다.](https://github.com/OfficeDev/MCCA#overview)</span><span class="sxs-lookup"><span data-stu-id="974da-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="974da-112">이 페이지에서는 선행 구성에 대한 자세한 정보를 제공하며 전체 설치 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="974da-113">이 페이지에 액세스하려면 GitHub 계정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="974da-114">**가용성:** MCCA는 Office 365 및 Microsoft 365 라이선스와 GCC(미국 정부 커뮤니티) 보통 및 GCC High 고객을 통해 모든 조직에서 사용할 수 있으며 DOD 고객에게 서비스를 확장할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="974da-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate and GCC High customers, with plans underway to expand service to DOD customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="974da-115">MCCA 설치 및 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="974da-115">Install MCCA and run a report</span></span>

<span data-ttu-id="974da-116">MCCA 도구를 설치하려면 다음을 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="974da-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="974da-117">도구를 다운로드하여 설치한 후 보고서를 실행하기 위해 이러한 단계를 반복할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="974da-118">MCCA를 열 때마다 로그인 자격 증명을 묻고 업데이트된 새 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="974da-119">1단계: 설치 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="974da-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="974da-120">먼저 PowerShell 갤러리에서 사용할 수 있는 Exchange Online PowerShell 모듈(v2.0.3 이상)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="974da-121">[설치 지침을 을(를) 얻습니다.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)</span><span class="sxs-lookup"><span data-stu-id="974da-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="974da-122">2단계: MCCA 설치</span><span class="sxs-lookup"><span data-stu-id="974da-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="974da-123">MCCA를 설치하려면 관리자 모드에서 PowerShell을 사용하여 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="974da-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="974da-124">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="974da-124">Follow the steps below:</span></span>

1. <span data-ttu-id="974da-125">Windows 시작 **단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="974da-126">**PowerShell을 입력하고** 마우스 오른쪽 단추로 Windows PowerShell **를** 클릭한 다음 **관리자 권한으로 실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="974da-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="974da-127">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="974da-128">3단계: 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="974da-128">Step 3: Run a report</span></span>

<span data-ttu-id="974da-129">MCCA를 설치한 후 MCCA를 실행하고 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="974da-130">보고서를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-130">To run a report:</span></span>

1. <span data-ttu-id="974da-131">PowerShell 열기</span><span class="sxs-lookup"><span data-stu-id="974da-131">Open PowerShell</span></span>
2. <span data-ttu-id="974da-132">cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```

   <span data-ttu-id="974da-133">GCC High 고객인 경우 보고서를 실행하려면 추가 입력 매개 변수를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-133">If you're a GCC High customer, you'll need to provide an additional input parameter to run the report:</span></span>

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. <span data-ttu-id="974da-134">MCCA가 실행된 후 초기 버전 확인을 통해 자격 증명을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-134">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="974da-135">사용자 이름 입력 프롬프트에서 Microsoft 365 계정 전자 메일 주소로 로그인합니다( 보고서를 만들 수 있는 역할[보기).](#role-based-reporting)</span><span class="sxs-lookup"><span data-stu-id="974da-135">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="974da-136">그런 다음 암호 프롬프트에 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-136">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="974da-137">그러면 보고서가 생성되는 데 약 2~5분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="974da-137">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="974da-138">완료되면 브라우저 창이 열리며 HTML 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="974da-138">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="974da-139">도구를 실행할 때마다 자격 증명을 요청하고 새 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-139">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="974da-140">이 보고서는 다음 디렉터리에 로컬로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="974da-140">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="974da-141">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="974da-141">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="974da-142">이 디렉터리에서 이전에 생성된 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-142">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="974da-143">보고서 이해</span><span class="sxs-lookup"><span data-stu-id="974da-143">Understanding your report</span></span>

<span data-ttu-id="974da-144">보고서에는 보고서가 생성된 날짜와 시간을 기준으로 데이터가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="974da-144">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="974da-145">맨 위 섹션에서는 생성된 경우, 조직 이름 및 테넌트 ID에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-145">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="974da-146">지리적 위치 기반 보고</span><span class="sxs-lookup"><span data-stu-id="974da-146">Geolocation-based reporting</span></span>

<span data-ttu-id="974da-147">참고 **섹션에는** 테넌트의 지리적 위치에 따라 보고서가 사용자 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-147">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="974da-148">도구에 나열된 권장 사항은 해당 국가 또는 지역에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-148">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="974da-149">지리적 위치 선택은 해당 지리적 위치와 관련된 중요한 정보 유형(SITS)을 평가하고 해당 국가 또는 지역에 맞게 보고서를 생성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="974da-149">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="974da-150">테넌트에 있는 데이터에 따라 지리적 지역을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="974da-150">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="974da-151">보고서의 위치 정보를 변경하려면 지리적 위치(-Geo) 입력 매개 변수를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-151">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="974da-152">테넌트에 적용할 수 있는 지리적 위치 중 하나 또는 여러 개를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-152">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="974da-153">다음 지침에 따라 특정 위치에 따라 보고서를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-153">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="974da-154">PowerShell 열기</span><span class="sxs-lookup"><span data-stu-id="974da-154">Open PowerShell</span></span>
2. <span data-ttu-id="974da-155">특정 지역을 지정하기 위해 아래 표의 국가 또는 지역에 해당하는 숫자를 사용하여 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-155">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="974da-156">여러 번호를 콤보로 구분하여 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-156">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="974da-157">예를 들어 아래 cmdlet은 Asia-Pacific 사용자 지정 보고서를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-157">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="974da-158">입력</span><span class="sxs-lookup"><span data-stu-id="974da-158">Input</span></span> |  <span data-ttu-id="974da-159">국가 또는 지역</span><span class="sxs-lookup"><span data-stu-id="974da-159">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="974da-160">1</span><span class="sxs-lookup"><span data-stu-id="974da-160">1</span></span> | <span data-ttu-id="974da-161">아시아 태평양</span><span class="sxs-lookup"><span data-stu-id="974da-161">Asia-Pacific</span></span> |
  | <span data-ttu-id="974da-162">2 </span><span class="sxs-lookup"><span data-stu-id="974da-162">2</span></span> | <span data-ttu-id="974da-163">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="974da-163">Australia</span></span> |
  | <span data-ttu-id="974da-164">3 </span><span class="sxs-lookup"><span data-stu-id="974da-164">3</span></span> | <span data-ttu-id="974da-165">캐나다</span><span class="sxs-lookup"><span data-stu-id="974da-165">Canada</span></span> |
  | <span data-ttu-id="974da-166">4 </span><span class="sxs-lookup"><span data-stu-id="974da-166">4</span></span> | <span data-ttu-id="974da-167">유럽(프랑스 제외) /중동/아프리카</span><span class="sxs-lookup"><span data-stu-id="974da-167">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="974da-168">5 </span><span class="sxs-lookup"><span data-stu-id="974da-168">5</span></span> | <span data-ttu-id="974da-169">프랑스</span><span class="sxs-lookup"><span data-stu-id="974da-169">France</span></span> |
  | <span data-ttu-id="974da-170">6 </span><span class="sxs-lookup"><span data-stu-id="974da-170">6</span></span> | <span data-ttu-id="974da-171">인도</span><span class="sxs-lookup"><span data-stu-id="974da-171">India</span></span> |
  | <span data-ttu-id="974da-172">7 </span><span class="sxs-lookup"><span data-stu-id="974da-172">7</span></span> | <span data-ttu-id="974da-173">일본</span><span class="sxs-lookup"><span data-stu-id="974da-173">Japan</span></span> |
  | <span data-ttu-id="974da-174">8 </span><span class="sxs-lookup"><span data-stu-id="974da-174">8</span></span> | <span data-ttu-id="974da-175">한국</span><span class="sxs-lookup"><span data-stu-id="974da-175">Korea</span></span> |
  | <span data-ttu-id="974da-176">9 </span><span class="sxs-lookup"><span data-stu-id="974da-176">9</span></span> | <span data-ttu-id="974da-177">북미(캐나다 제외)</span><span class="sxs-lookup"><span data-stu-id="974da-177">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="974da-178">10  </span><span class="sxs-lookup"><span data-stu-id="974da-178">10</span></span> | <span data-ttu-id="974da-179">남미</span><span class="sxs-lookup"><span data-stu-id="974da-179">South America</span></span> |
  | <span data-ttu-id="974da-180">11 </span><span class="sxs-lookup"><span data-stu-id="974da-180">11</span></span> | <span data-ttu-id="974da-181">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="974da-181">South Africa</span></span> |
  | <span data-ttu-id="974da-182">12 </span><span class="sxs-lookup"><span data-stu-id="974da-182">12</span></span> | <span data-ttu-id="974da-183">스위스</span><span class="sxs-lookup"><span data-stu-id="974da-183">Switzerland</span></span> |
  | <span data-ttu-id="974da-184">13 </span><span class="sxs-lookup"><span data-stu-id="974da-184">13</span></span> | <span data-ttu-id="974da-185">아랍에미리트</span><span class="sxs-lookup"><span data-stu-id="974da-185">United Arab Emirates</span></span> |
  | <span data-ttu-id="974da-186">14 </span><span class="sxs-lookup"><span data-stu-id="974da-186">14</span></span> | <span data-ttu-id="974da-187">영국</span><span class="sxs-lookup"><span data-stu-id="974da-187">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="974da-188">보고서에는 항상 MCCA에서 지원하는 SWIFT 코드, 신용 카드 번호 등의 국제 중요한 정보 유형이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="974da-188">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="974da-189">역할 기반 보고</span><span class="sxs-lookup"><span data-stu-id="974da-189">Role-based reporting</span></span>

<span data-ttu-id="974da-190">또한 역할에 따라 보고서가 사용자 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="974da-190">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="974da-191">아래 표에는 보고서의 어떤 섹션에 액세스할 수 있는 역할이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="974da-191">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="974da-192">아래 표에 나열되지 않은 조직 내의 다른 역할은 도구를 실행하지 못하거나 도구를 실행하여 최종 보고서의 정보에 제한적으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-192">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="974da-193">![MCCA - 역할](../media/compliance-manager-mcca-roles.png "MCCA 역할")</span><span class="sxs-lookup"><span data-stu-id="974da-193">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="974da-194">예외:</span><span class="sxs-lookup"><span data-stu-id="974da-194">Exceptions:</span></span>
1. <span data-ttu-id="974da-195">사용자는 "Exchange Online에 IRM 사용" 섹션과 별도로 IP에 대한 보고서를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-195">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="974da-196">사용자는 "Exchange Online에 IRM 사용" 섹션과 별도로 IP에 대한 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-196">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="974da-197">사용자는 "O365에서 통신 규정 준수 사용" 섹션과 별도로 IP에 대한 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-197">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="974da-198">사용자는 "Office 365에서 감사 사용" 섹션과 별도로 IP에 대한 보고서를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-198">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="974da-199">사용자는 "Office 365에서 감사 사용" 섹션과 별도로 IP에 대한 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-199">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="974da-200">솔루션 요약 섹션</span><span class="sxs-lookup"><span data-stu-id="974da-200">Solutions Summary section</span></span>

<span data-ttu-id="974da-201">보고서의 **솔루션 요약** 섹션에서는 규정 준수 관리자에서 조직이 준수 자세를 개선하는 데 도움을 줄 수 있는 개선 작업에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-201">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="974da-202">![MCCA - 솔루션 요약](../media/compliance-manager-mcca-solutions.png "MCCA 솔루션 요약 화면")</span><span class="sxs-lookup"><span data-stu-id="974da-202">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="974da-203">MCCA는 준수 관리자의 권장 개선 작업에 대해 현재 구성을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-203">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="974da-204">주의가 필요한 것으로 MCCA 도구에서 식별된 모든 개선 작업이 이 섹션에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="974da-204">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="974da-205">각 Microsoft 솔루션 옆에는 준수 관리자의 개선 작업에 해당하는 항목 수를 나타내는 색으로 코딩된 상자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-205">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="974da-206">작업은 다음 세 가지 상태로 나됩니다.</span><span class="sxs-lookup"><span data-stu-id="974da-206">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="974da-207">**확인**: 권장 조건을 충족하며 현재 주의가 필요 없는 작업</span><span class="sxs-lookup"><span data-stu-id="974da-207">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="974da-208">**개선** 사항 : 주의가 필요한 작업</span><span class="sxs-lookup"><span data-stu-id="974da-208">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="974da-209">**권장 사항:** 주의가 필요 없지만 모범 사례를 권장하는 작업</span><span class="sxs-lookup"><span data-stu-id="974da-209">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="974da-210">개선 사항 및 권장 사항을 확인하려면 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-210">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="974da-211">**개선 상태가 있는 항목**</span><span class="sxs-lookup"><span data-stu-id="974da-211">**Items with the Improvement status**</span></span>

<span data-ttu-id="974da-212">개선 작업 오른쪽의  개선 레이블 옆에 있는 드롭다운을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-212">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="974da-213">현재 설정에 대한 빠른 요약 및 세부 정보 및 권장 개선 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="974da-213">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="974da-214">요약에는 준수 관리자에 대한 직접 링크, Microsoft 365 규정 준수 센터의 해당 솔루션 및 관련 설명서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-214">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="974da-215">준수 관리자 링크를 클릭하면 아직 구현하지 않은 해당 솔루션 내의 모든 개선 작업을 필터링된 보기로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-215">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="974da-216">이 지점에서 준수 점수를 높이기 위해 달성할 [](compliance-score-calculation.md)수 있는 포인트 수와 해당 점수가 적용되는 평가, 적용 가능한 규정 및 인증을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-216">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="974da-217">DLP의 경우 권장되는  정보를 기반으로 미리 생성된 PowerShell 스크립트를 제공하는 재구성 스크립트 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-217">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="974da-218">PowerShell 콘솔에서 직접 복사하여 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-218">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="974da-219">테스트 모드에서 DLP 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-219">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="974da-220">**추천 상태가 있는 항목**</span><span class="sxs-lookup"><span data-stu-id="974da-220">**Items with Recommendation status**</span></span>

<span data-ttu-id="974da-221">개선 작업 오른쪽의  추천 레이블 옆에 있는 드롭다운을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-221">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="974da-222">개선 작업과 관련된 조직의 현재 Microsoft 365 환경에 대한 요약과 권장 모범 사례를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="974da-222">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="974da-223">리소스</span><span class="sxs-lookup"><span data-stu-id="974da-223">Resources</span></span>

<span data-ttu-id="974da-224">MCCA 설치, 설정 및 사용에 대한 자세한 내용은 [GitHub의 README](https://github.com/OfficeDev/MCCA#overview) 지침을 참조하세요(GitHub 계정 필요 없음).</span><span class="sxs-lookup"><span data-stu-id="974da-224">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="974da-225">자세한 내용은 Windows PowerShell PowerShell 설명서를 사용하는 방법을 [참조하세요.](/powershell/scripting/how-to-use-docs?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="974da-225">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="974da-226">자세한 내용은 [시작 Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)참조합니다.</span><span class="sxs-lookup"><span data-stu-id="974da-226">See also [Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>