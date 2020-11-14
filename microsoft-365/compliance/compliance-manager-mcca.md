---
title: 준수 관리자를 위한 Microsoft 준수 구성 분석기
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
description: Microsoft 준수 구성 분석기를 사용 하 여 Microsoft 준수 관리자를 통해 신속 하 게 시작 하 고 실행 하는 방법을 이해 합니다.
ms.openlocfilehash: 1f7d987262a7d390cb9efe2162ae9be9f56c8757
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49072007"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager"></a><span data-ttu-id="5d634-103">준수 관리자를 위한 Microsoft 준수 구성 분석기</span><span class="sxs-lookup"><span data-stu-id="5d634-103">Microsoft Compliance Configuration Analyzer for Compliance Manager</span></span>

<span data-ttu-id="5d634-104">**이 문서의 내용** Microsoft 규정 준수 구성 분석기 도구를 설치 하 고 실행 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-overview"></a><span data-ttu-id="5d634-105">MCCA (Microsoft 준수 구성 분석기) 개요</span><span class="sxs-lookup"><span data-stu-id="5d634-105">Microsoft Compliance Configuration Analyzer (MCCA) overview</span></span>

<span data-ttu-id="5d634-106">Microsoft 규정 준수 구성 분석기 (MCCA)는 [Microsoft 준수 관리자](compliance-manager.md)를 시작 하는 데 도움이 되는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="5d634-107">MCCA는 조직의 현재 구성을 페치하고 Microsoft 365 권장 모범 사례에 따라 유효성을 검사 하는 PowerShell 기반 유틸리티입니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="5d634-108">이러한 모범 사례는 데이터 보호 및 데이터 관리를 위한 주요 규정 및 표준을 포함 하는 컨트롤 집합을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="5d634-109">MCCA를 통해 준수 관리자의 현재 Microsoft 365 환경에 적용 되는 개선 조치를 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="5d634-110">MCCA로 식별 되는 각 작업은 준수 관리자에 대 한 직접 링크 및 정정 작업 수행을 시작할 수 있는 적절 한 솔루션을 포함 하 여 구현에 대 한 권장 사항을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="5d634-111">MCCA를 이해 하는 데 사용할 수 있는 추가 리소스는 [GitHub의 추가 정보를 참조](https://github.com/OfficeDev/MCCA#overview)하세요.</span><span class="sxs-lookup"><span data-stu-id="5d634-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="5d634-112">이 페이지에서는 필수 구성 요소에 대 한 자세한 정보를 제공 하 고 전체 설치 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="5d634-113">이 페이지에 액세스 하려면 GitHub 계정이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-113">You don’t need a GitHub account to access this page.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="5d634-114">MCCA 설치 및 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="5d634-114">Install MCCA and run a report</span></span>

<span data-ttu-id="5d634-115">Windows PowerShell을 사용 하 여 MCCA 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-115">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="5d634-116">이 도구를 다운로드 하 고 설치한 후에는 이러한 단계를 반복 하 여 보고서를 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-116">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="5d634-117">MCCA를 열 때마다 로그인 자격 증명을 묻는 메시지가 표시 되 고 업데이트 된 새 보고서가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-117">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="5d634-118">1 단계: Windows PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="5d634-118">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="5d634-119">시작 하려면 PowerShell 갤러리에서 사용할 수 있는 Exchange Online PowerShell 모듈 (v 2.0.3 이상)이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-119">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="5d634-120">[설치 지침을 가져옵니다](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span><span class="sxs-lookup"><span data-stu-id="5d634-120">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="5d634-121">2 단계: MCCA 설치</span><span class="sxs-lookup"><span data-stu-id="5d634-121">Step 2: Install MCCA</span></span>

<span data-ttu-id="5d634-122">MCCA를 설치 하려면 관리자 모드에서 PowerShell을 사용 하 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-122">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="5d634-123">아래 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-123">Follow the steps below:</span></span>

1. <span data-ttu-id="5d634-124">Windows **시작** 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-124">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="5d634-125">**Powershell** 을 입력 하 고 **Windows powershell** 을 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-125">Type **PowerShell** , right-click on **Windows PowerShell** , then select **Run as administrator**.</span></span>
1. <span data-ttu-id="5d634-126">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-126">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="5d634-127">3 단계: 보고서 실행</span><span class="sxs-lookup"><span data-stu-id="5d634-127">Step 3: Run a report</span></span>

<span data-ttu-id="5d634-128">MCCA를 설치한 후에는 MCCA를 실행 하 고 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-128">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="5d634-129">보고서를 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="5d634-129">To run a report:</span></span>

1. <span data-ttu-id="5d634-130">PowerShell 열기</span><span class="sxs-lookup"><span data-stu-id="5d634-130">Open PowerShell</span></span>
2. <span data-ttu-id="5d634-131">Cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-131">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```
3. <span data-ttu-id="5d634-132">MCCA가 실행 되 면 초기 버전 확인을 수행 하 고 자격 증명을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-132">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="5d634-133">사용자 이름 입력 프롬프트에서 Microsoft 365 계정 전자 메일 주소로 로그인 합니다 ([보고서를 만들 수 있는 역할 보기](#role-based-reporting)).</span><span class="sxs-lookup"><span data-stu-id="5d634-133">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="5d634-134">암호를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-134">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="5d634-135">보고서를 생성 하는 데 약 2-5 분 정도 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-135">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="5d634-136">작업이 완료 되 면 브라우저 창이 열리고 HTML 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-136">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="5d634-137">이 도구를 실행할 때마다 자격 증명을 묻는 메시지가 표시 되 고 새 보고서가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-137">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="5d634-138">이 보고서는 다음 디렉터리에 로컬로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-138">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="5d634-139">C:\Users \<username> \AppData\Local\Microsoft\MCCA.</span><span class="sxs-lookup"><span data-stu-id="5d634-139">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="5d634-140">이 디렉터리에서 이전에 생성 된 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-140">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="5d634-141">보고서 이해</span><span class="sxs-lookup"><span data-stu-id="5d634-141">Understanding your report</span></span>

<span data-ttu-id="5d634-142">보고서가 생성 된 날짜 및 시간을 기준으로 데이터를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-142">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="5d634-143">맨 위 섹션에는 생성 된 시기, 조직 이름 및 테 넌 트 ID에 대 한 세부 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-143">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="5d634-144">지리적 위치 기반 보고</span><span class="sxs-lookup"><span data-stu-id="5d634-144">Geolocation-based reporting</span></span>

<span data-ttu-id="5d634-145">**메모** 섹션에는 테 넌 트의 지리적 위치에 따라 보고서가 사용자 지정 된 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-145">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="5d634-146">이 도구에 나열 된 권장 사항은 해당 국가나 지역에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-146">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="5d634-147">지리적 위치 선택은 해당 지리적 위치와 관련 된 중요 한 정보 유형 (현재 위치)을 평가 하 고 해당 국가나 지역에 맞는 보고서를 생성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-147">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="5d634-148">테 넌 트에 있는 데이터를 기반으로 geolocations를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-148">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="5d634-149">보고서의 위치 정보를 변경 하려면 location (-Geo) 입력 매개 변수를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-149">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="5d634-150">테 넌 트에 적용 가능한 geolocations를 하나 또는 여러 개 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-150">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="5d634-151">다음 지침에 따라 특정 위치에 따라 보고서를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-151">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="5d634-152">PowerShell 열기</span><span class="sxs-lookup"><span data-stu-id="5d634-152">Open PowerShell</span></span>
2. <span data-ttu-id="5d634-153">특정 지역을 지정 하려면 아래 표에서 해당 국가 또는 지역에 해당 하는 번호를 사용 하 여 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-153">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="5d634-154">여러 숫자를 쉼표로 구분 하 여 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-154">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="5d634-155">예를 들어 아래 cmdlet은 Asia-Pacific 및 일본에 대해 사용자 지정 된 보고서를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-155">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="5d634-156">입력</span><span class="sxs-lookup"><span data-stu-id="5d634-156">Input</span></span> |  <span data-ttu-id="5d634-157">국가 또는 지역</span><span class="sxs-lookup"><span data-stu-id="5d634-157">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="5d634-158">1 </span><span class="sxs-lookup"><span data-stu-id="5d634-158">1</span></span> | <span data-ttu-id="5d634-159">아시아 태평양</span><span class="sxs-lookup"><span data-stu-id="5d634-159">Asia-Pacific</span></span> |
  | <span data-ttu-id="5d634-160">2 </span><span class="sxs-lookup"><span data-stu-id="5d634-160">2</span></span> | <span data-ttu-id="5d634-161">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="5d634-161">Australia</span></span> |
  | <span data-ttu-id="5d634-162">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="5d634-162">3</span></span> | <span data-ttu-id="5d634-163">캐나다</span><span class="sxs-lookup"><span data-stu-id="5d634-163">Canada</span></span> |
  | <span data-ttu-id="5d634-164">4 </span><span class="sxs-lookup"><span data-stu-id="5d634-164">4</span></span> | <span data-ttu-id="5d634-165">유럽 (프랑스 제외)/중동/아프리카</span><span class="sxs-lookup"><span data-stu-id="5d634-165">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="5d634-166">5 </span><span class="sxs-lookup"><span data-stu-id="5d634-166">5</span></span> | <span data-ttu-id="5d634-167">프랑스</span><span class="sxs-lookup"><span data-stu-id="5d634-167">France</span></span> |
  | <span data-ttu-id="5d634-168">6 </span><span class="sxs-lookup"><span data-stu-id="5d634-168">6</span></span> | <span data-ttu-id="5d634-169">인도</span><span class="sxs-lookup"><span data-stu-id="5d634-169">India</span></span> |
  | <span data-ttu-id="5d634-170">7 </span><span class="sxs-lookup"><span data-stu-id="5d634-170">7</span></span> | <span data-ttu-id="5d634-171">일본</span><span class="sxs-lookup"><span data-stu-id="5d634-171">Japan</span></span> |
  | <span data-ttu-id="5d634-172">8 </span><span class="sxs-lookup"><span data-stu-id="5d634-172">8</span></span> | <span data-ttu-id="5d634-173">한국</span><span class="sxs-lookup"><span data-stu-id="5d634-173">Korea</span></span> |
  | <span data-ttu-id="5d634-174">9 </span><span class="sxs-lookup"><span data-stu-id="5d634-174">9</span></span> | <span data-ttu-id="5d634-175">북미 (캐나다 제외)</span><span class="sxs-lookup"><span data-stu-id="5d634-175">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="5d634-176">10 </span><span class="sxs-lookup"><span data-stu-id="5d634-176">10</span></span> | <span data-ttu-id="5d634-177">남미</span><span class="sxs-lookup"><span data-stu-id="5d634-177">South America</span></span> |
  | <span data-ttu-id="5d634-178">11 </span><span class="sxs-lookup"><span data-stu-id="5d634-178">11</span></span> | <span data-ttu-id="5d634-179">남아프리카 공화국</span><span class="sxs-lookup"><span data-stu-id="5d634-179">South Africa</span></span> |
  | <span data-ttu-id="5d634-180">12 </span><span class="sxs-lookup"><span data-stu-id="5d634-180">12</span></span> | <span data-ttu-id="5d634-181">스위스</span><span class="sxs-lookup"><span data-stu-id="5d634-181">Switzerland</span></span> |
  | <span data-ttu-id="5d634-182">13 </span><span class="sxs-lookup"><span data-stu-id="5d634-182">13</span></span> | <span data-ttu-id="5d634-183">아랍에미리트</span><span class="sxs-lookup"><span data-stu-id="5d634-183">United Arab Emirates</span></span> |
  | <span data-ttu-id="5d634-184">14 </span><span class="sxs-lookup"><span data-stu-id="5d634-184">14</span></span> | <span data-ttu-id="5d634-185">영국</span><span class="sxs-lookup"><span data-stu-id="5d634-185">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="5d634-186">보고서에는 항상 SWIFT code, 신용 카드 번호 등의 MCCA에서 지 원하는 국제 중요 한 정보 유형이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-186">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="5d634-187">역할 기반 보고</span><span class="sxs-lookup"><span data-stu-id="5d634-187">Role-based reporting</span></span>

<span data-ttu-id="5d634-188">사용자의 역할에 따라 보고서도 사용자 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-188">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="5d634-189">아래 표에는 보고서의 각 섹션에 대 한 액세스 권한이 있는 역할이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-189">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="5d634-190">조직 내의 다른 역할 (아래 표에 나열 되지 않음)은 도구를 실행 하지 못할 수도 있고, 도구를 실행 하 여 최종 보고서의 정보에 대 한 제한 된 액세스를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-190">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="5d634-191">![MCCA-역할](../media/compliance-manager-mcca-roles.png "MCCA 역할")</span><span class="sxs-lookup"><span data-stu-id="5d634-191">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="5d634-192">예외</span><span class="sxs-lookup"><span data-stu-id="5d634-192">Exceptions:</span></span>
1. <span data-ttu-id="5d634-193">사용자가 "Exchange Online에 IRM 사용" 섹션에서 IP에 대 한 보고서를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-193">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="5d634-194">사용자가 "Exchange Online에 IRM 사용" 섹션에서 IP에 대 한 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-194">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="5d634-195">사용자는 "O365에서 통신 준수 기능 설정" 섹션에서 IP를 사용할 수 있는 보고서를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-195">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="5d634-196">사용자는 "Office 365에서 감사 기능 설정" 섹션에서 IP를 사용 하지 않도록 보고서를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-196">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="5d634-197">사용자가 "Office 365의 감사 사용" 섹션에서 IP에 대 한 보고서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-197">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="5d634-198">솔루션 요약 섹션</span><span class="sxs-lookup"><span data-stu-id="5d634-198">Solutions Summary section</span></span>

<span data-ttu-id="5d634-199">보고서의 **솔루션 요약** 섹션에서는 조직이 준수 관리자에 게 준수 상태를 향상 시키는 데 사용할 수 있는 개선 작업에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-199">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="5d634-200">![MCCA-솔루션 요약](../media/compliance-manager-mcca-solutions.png "MCCA 솔루션 요약 화면")</span><span class="sxs-lookup"><span data-stu-id="5d634-200">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="5d634-201">MCCA는 준수 관리자의 권장 향상 작업과 비교 하 여 현재 구성을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-201">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="5d634-202">이 섹션에서는 MCCA 도구로 식별 되는 모든 개선 작업을 주의가 필요한 것으로 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-202">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="5d634-203">각 Microsoft 솔루션 옆에는 준수 관리자의 향상 작업에 해당 하는 항목 수를 나타내는 색으로 구분 된 입력란이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-203">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="5d634-204">이 작업은 다음과 같은 세 가지 상태 상태로 나누어집니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-204">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="5d634-205">**정상** : 권장 조건을 충족 하며 지금은 주의 하지 않아도 되는 작업</span><span class="sxs-lookup"><span data-stu-id="5d634-205">**OK** : the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="5d634-206">**개선** : 주의가 필요한 작업</span><span class="sxs-lookup"><span data-stu-id="5d634-206">**Improvement** : actions that need attention</span></span>
- <span data-ttu-id="5d634-207">**권장 사항** : 주의가 필요 하지 않지만 모범 사례를 제안 하는 작업</span><span class="sxs-lookup"><span data-stu-id="5d634-207">**Recommendation** : actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="5d634-208">향상 된 기능 및 권장 사항을 보려면 상자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-208">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="5d634-209">**개선 상태인 항목**</span><span class="sxs-lookup"><span data-stu-id="5d634-209">**Items with the Improvement status**</span></span>

<span data-ttu-id="5d634-210">개선 작업의 오른쪽에 있는 **개선** 레이블 옆의 드롭다운을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-210">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="5d634-211">현재 설정 및 권장 되는 개선 작업에 대 한 간략 한 요약 및 세부 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-211">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="5d634-212">이 요약에는 준수 관리자, Microsoft 365 준수 센터의 해당 솔루션 및 관련 설명서에 대 한 직접 링크가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-212">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="5d634-213">준수 관리자 링크를 클릭 하면 아직 구현 되지 않은 솔루션 내의 모든 개선 작업에 대 한 필터링 된 보기로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-213">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="5d634-214">여기에서 [준수 점수](compliance-score-calculation.md)를 높이는 데 사용할 수 있는 점 수와 해당 규정 및 인증에 대 한 평가를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-214">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="5d634-215">DLP에는 권장 사항에 따라 미리 생성 된 PowerShell 스크립트를 제공 하는 **수정 스크립트** 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-215">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="5d634-216">PowerShell 콘솔에서 직접 복사 하 여 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-216">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="5d634-217">테스트 모드에서 DLP 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-217">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="5d634-218">**추천 상태가 포함 된 항목**</span><span class="sxs-lookup"><span data-stu-id="5d634-218">**Items with Recommendation status**</span></span>

<span data-ttu-id="5d634-219">개선 작업 오른쪽에 있는 **추천** 레이블 옆의 드롭다운을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-219">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="5d634-220">개선 작업과 관련 된 조직의 현재 Microsoft 365 환경에 대 한 요약 정보와 권장 모범 사례를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d634-220">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="5d634-221">리소스</span><span class="sxs-lookup"><span data-stu-id="5d634-221">Resources</span></span>

<span data-ttu-id="5d634-222">MCCA를 설치, 설정 및 사용 하는 방법에 대 한 자세한 내용은 GitHub (GitHub 계정 필요 없음) [의 README 지침](https://github.com/OfficeDev/MCCA#overview) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d634-222">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="5d634-223">Windows PowerShell에 대 한 자세한 내용을 보려면 [PowerShell 설명서 사용 방법을](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)시작 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d634-223">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="5d634-224">[Windows PowerShell 시작](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)도 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d634-224">See also [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
