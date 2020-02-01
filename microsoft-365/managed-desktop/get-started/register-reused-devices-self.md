---
title: 직접 기존의 장치 등록
description: 다시 사용 가능한 장치를 등록 하 여 Microsoft Managed Desktop에서 관리할 수 있도록 할 수도 있습니다.
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: e41d2ac66dea6640978435390bf3a8868c7cec7c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596535"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="74ace-103">직접 기존의 장치 등록</span><span class="sxs-lookup"><span data-stu-id="74ace-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="74ace-104">이 항목에서는 이미 갖고 있는 장치를 다시 사용 하 고 Microsoft Managed Desktop에 등록 하는 단계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="74ace-105">새 장치에 대 한 작업을 수행 하는 경우 대신 [Microsoft Managed Desktop의 새 장치 등록](register-devices-self.md) 에 설명 된 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="74ace-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="74ace-106">파트너에 대 한 프로세스는 [파트너가 장치를 등록 하기 위한 단계](register-devices-partner.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="74ace-107">Microsoft Managed Desktop은 새로운 장치에서 작동 하거나 이미 사용 중인 장치를 다시 사용할 수 있습니다 (다시 이미지 해야 함).</span><span class="sxs-lookup"><span data-stu-id="74ace-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="74ace-108">Azure Portal에서 Microsoft Managed Desktop을 사용 하 여 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-108">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="74ace-109">기존 장치 등록 준비</span><span class="sxs-lookup"><span data-stu-id="74ace-109">Prepare to register existing devices</span></span>


<span data-ttu-id="74ace-110">기존 장치를 등록 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="74ace-111">각 장치에 대 한 하드웨어 해시를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="74ace-112">해시 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="74ace-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="74ace-113">[Microsoft Managed Desktop에서 장치를 등록](#register-devices)합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-113">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="74ace-114">이미지가 올바른지 다시 한 번 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="74ace-115">장치 배달</span><span class="sxs-lookup"><span data-stu-id="74ace-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="74ace-116">하드웨어 해시 가져오기</span><span class="sxs-lookup"><span data-stu-id="74ace-116">Obtain the hardware hash</span></span>

<span data-ttu-id="74ace-117">Microsoft Managed Desktop은 해당 하드웨어 해시를 참조 하 여 각 장치를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="74ace-118">이미 사용 중인 장치에서이 정보를 가져올 수 있는 옵션은 다음 네 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="74ace-119">OEM 공급자에 게 하드웨어 해시를 포함 하는 AutoPilot 등록 파일에 대해 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="74ace-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="74ace-120">[Configuration Manager](#configuration-manager)에서 사용자 지정 보고서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-120">Create a custom report in [Configuration Manager](#configuration-manager).</span></span>
- <span data-ttu-id="74ace-121">[Active Directory](#active-directory-powershell-script-method) 를 사용 하거나 각 장치에서 [수동으로](#manual-powershell-script-method) Windows PowerShell 스크립트를 실행 하 고 파일에서 결과를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="74ace-122">각 장치를 시작 하지만 Windows 설치 환경을 완료 하지 않고 [이동식 플래시 드라이브에서 해시를 수집](#flash-drive-method)합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="configuration-manager"></a><span data-ttu-id="74ace-123">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="74ace-123">Configuration Manager</span></span>

<span data-ttu-id="74ace-124">Microsoft Endpoint Configuration Manager를 사용 하 여 Microsoft Managed Desktop에 등록 하려는 기존 장치의 하드웨어 해시를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74ace-125">이 정보를 가져올 장치에는 Windows 10, 버전 1703 이상을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> <span data-ttu-id="74ace-126">구성 관리자 (현재 분기) 사이트에 연결 된 구성 관리자 클라이언트도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-126">You also need a device that is a Configuration Manager client connected to the Configuration Manager (Current Branch) site.</span></span> <span data-ttu-id="74ace-127">또한 SQL Server Reporting Services를 사용 하 여 환경에 보고 지점 사이트 시스템 역할이 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-127">You also need the Reporting Point Site System role set up in your environment with SQL Server Reporting Services enabled.</span></span> 

<span data-ttu-id="74ace-128">이러한 필수 구성 요소를 모두 충족 하면 다음 단계를 수행 하 여 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-128">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="74ace-129">Configuration Manager 콘솔에서 **모니터링**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-129">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="74ace-130">모니터링 작업 영역에서 **보고**를 확장 한 다음 **보고서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-130">In the Monitoring workspace, expand **Reporting**, and then select **Reports**.</span></span> 
3. <span data-ttu-id="74ace-131">**홈** 탭의 **만들기** 섹션에서 **보고서 만들기** 를 선택 하 여 보고서 만들기 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-131">On the **Home** tab, in the **Create** section, select **Create Report** to open the Create Report wizard.</span></span> 
4. <span data-ttu-id="74ace-132">**정보** 페이지에서 다음 설정을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-132">On the **Information** page, set these settings:</span></span> 
    - <span data-ttu-id="74ace-133">**이름:** 보고서의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-133">**Name:** Specify a name for the report.</span></span> 
    - <span data-ttu-id="74ace-134">**설명:** 보고서에 대 한 설명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-134">**Description:** Specify a description for the report.</span></span> 
    - <span data-ttu-id="74ace-135">**서버:** 이 보고서를 만들 보고서 서버의 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-135">**Server:** Displays the name of the report server on which you are creating this report.</span></span> 
    - <span data-ttu-id="74ace-136">**경로:** **찾아보기를** 선택 하 여 보고서를 저장할 폴더를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-136">**Path:** Select **Browse** to specify a folder in which you want to store the report.</span></span> 
5. <span data-ttu-id="74ace-137"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="74ace-137">Select **Next**.</span></span> 
6. <span data-ttu-id="74ace-138">**요약** 페이지에서 설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-138">On the **Summary** page, review the settings.</span></span> <span data-ttu-id="74ace-139">설정을 변경 하거나 **다음** 을 선택 하 여 Configuration Manager에서 보고서를 만들려면 **이전** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-139">Select **Previous** to change the settings or select **Next** to create the report in Configuration Manager.</span></span> 
7. <span data-ttu-id="74ace-140">**완료** 페이지에서 **닫기를** 선택 하 여 마법사를 종료 하 고 보고서 **작성기** 를 열어 보고서 설정을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-140">On the **Completion** page, select **Close** to exit the wizard and open **Report Builder** to enter the report settings.</span></span> <span data-ttu-id="74ace-141">메시지가 표시 되 면 사용자 계정 및 암호를 입력 하 고 확인을 선택 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="74ace-141">Enter your user account and password if you are prompted, and then select **OK.**</span></span> <span data-ttu-id="74ace-142">장치에 Report Builder가 설치 되어 있지 않으면 설치 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-142">If Report Builder is not installed on the device, you are prompted to install it.</span></span> <span data-ttu-id="74ace-143">보고서를 수정 하 고 만드는 데 필요한 **Report Builder를 설치 하려면 실행을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-143">Select **Run to install Report Builder**, which is required to modify and create reports.</span></span> 


<span data-ttu-id="74ace-144">**Microsoft Report Builder에서**보고서에 대 한 SQL 문을 제공 하 고 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-144">**In Microsoft Report Builder**, provide the SQL statement for the report and follow these steps:</span></span>

1. <span data-ttu-id="74ace-145">왼쪽 창에서 데이터 집합을 **선택 하**고 마우스 오른쪽 단추를 클릭 하 여 **Dataset을 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-145">In the left pane, select **Datasets**, and then right-click to **Add Dataset**.</span></span>
2. <span data-ttu-id="74ace-146">**쿼리** 탭으로 이동한 다음 이름을 *DataSet0*로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-146">Go to the **Query** tab, and then enter the name as *DataSet0*.</span></span> 
3. <span data-ttu-id="74ace-147">**내 보고서에 포함 된 데이터 집합 사용을 선택 합니다**. 보고서 작성기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-147">Select **Use a dataset embedded in my report**; Report Builder opens.</span></span>
4. <span data-ttu-id="74ace-148">**보고서 작성기**에서 **데이터 원본:** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-148">In **Report Builder**, select **Data source:**.</span></span> <span data-ttu-id="74ace-149">"AutoGen"로 시작 하는 기본 데이터 원본을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-149">Select the default data source, which should start with "AutoGen".</span></span> 
5. <span data-ttu-id="74ace-150">**텍스트 형식 쿼리**를 선택 하 고 다음 쿼리를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-150">Choose **Query type as Text**, and then enter this query:</span></span>




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. <span data-ttu-id="74ace-151">**필드** 탭으로 이동 하 고 **필드 이름** 및 **필드 원본** 에 대 한 wehre 값을 이미 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-151">Navigate to the **Field** tab, wehre values for **Field Name** and **Field Source** should already be populated.</span></span> <span data-ttu-id="74ace-152">그렇지 않은 경우에는 **추가**를 선택한 다음 **쿼리 필드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-152">If they aren't, then select **Add**, and then select **Query Field**.</span></span> <span data-ttu-id="74ace-153">**필드 이름** 및 **필드 원본을**입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-153">Enter the **Field Name** and **Field Source**.</span></span>
6. <span data-ttu-id="74ace-154">다음 각 값에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-154">Repeat for each of these values:</span></span> 
    - <span data-ttu-id="74ace-155">회사</span><span class="sxs-lookup"><span data-stu-id="74ace-155">Manufacturer</span></span> 
    - <span data-ttu-id="74ace-156">모델</span><span class="sxs-lookup"><span data-stu-id="74ace-156">Model</span></span> 
    - <span data-ttu-id="74ace-157">Serial_Number</span><span class="sxs-lookup"><span data-stu-id="74ace-157">Serial_Number</span></span> 
    - <span data-ttu-id="74ace-158">HardwareHash</span><span class="sxs-lookup"><span data-stu-id="74ace-158">HardwareHash</span></span>
7. <span data-ttu-id="74ace-159">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-159">Select **OK**.</span></span>

<span data-ttu-id="74ace-160">**다음으로, 다음 단계를 수행 하 여 보고서 표시를 정의 하 고 보고서를 만듭니다** .</span><span class="sxs-lookup"><span data-stu-id="74ace-160">**Next, define the report display and create the report** by following these steps:</span></span>

1. <span data-ttu-id="74ace-161">**표 또는 행렬을**선택 하 고 새 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-161">Select **Table or Matrix**; a new wizard will open.</span></span>
2. <span data-ttu-id="74ace-162">**데이터 집합 선택**에서 **이 보고서 또는 공유 데이터 집합의 기존 데이터 집합 선택을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-162">In **Choose a dataset**, select **Choose an existing dataset in this report or a shared dataset**.</span></span>  
3. <span data-ttu-id="74ace-163">**DataSet0** (기본값)를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-163">Select **DataSet0** (the default), and then select **Next**.</span></span>
4. <span data-ttu-id="74ace-164">**제조업체**, **모델**및 **일련 번호** 를 **행 그룹** 상자에 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-164">Drag **Manufacturer**, **Model**, and **Serial Number** into the **Row Groups** box.</span></span> <span data-ttu-id="74ace-165">**HardwareHash** 을 **값** 상자에 끌어 놓고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-165">Drag **HardwareHash** into the **Values** box and then select **Next**.</span></span>
5. <span data-ttu-id="74ace-166">**부분합과 총합계 표시** 확인란의 선택을 취소 하 고 **그룹을 확장/축소**합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-166">Clear the checkboxes for **Show subtotals and grand totals** and **Expand/collapse groups**.</span></span> <span data-ttu-id="74ace-167"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="74ace-167">Select **Next**.</span></span>
6. <span data-ttu-id="74ace-168">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="74ace-168">Select **Finish**.</span></span>
7. <span data-ttu-id="74ace-169">**실행** 을 선택 하 여 보고서를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-169">Select **Run** to run your report.</span></span> <span data-ttu-id="74ace-170">보고서에서 예상 되는 정보를 제공 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-170">Verify that the report provides the information that you expect.</span></span> <span data-ttu-id="74ace-171">필요한 경우 **디자인** 을 선택 하 여 디자인 보기로 돌아간 다음 보고서를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-171">If necessary, select **Design** to return to the Design view to modify the report.</span></span>
8. <span data-ttu-id="74ace-172">**저장** 을 클릭 하 여 보고서를 보고서 서버에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-172">Select **Save** to save the report to the report server.</span></span> <span data-ttu-id="74ace-173">모니터링 작업 영역의 보고서 노드에서 새 보고서를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-173">You can run the new report in the Reports node in the Monitoring workspace.</span></span> 

<span data-ttu-id="74ace-174">마지막으로 다음 단계를 수행 하 여 **보고서를 내보내고 장치를 등록 하는 데 사용** 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-174">**Finally, export the report and use it to register devices** by following these steps.</span></span> <span data-ttu-id="74ace-175">이전 단계를 완료 한 후에 탐색 한 경우이 섹션의 1 단계와 2 단계만 진행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-175">(You should only need to follow Steps 1 and 2 of this section if you have navigated away after the previous steps.):</span></span>

1. <span data-ttu-id="74ace-176">Configuration Manager 콘솔에서 **모니터링**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-176">In the Configuration Manager console, select **Monitoring**.</span></span>
2. <span data-ttu-id="74ace-177">**모니터링**에서 **보고**를 확장 한 다음 **보고서**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-177">In **Monitoring**, expand **Reporting**, and then select **Reports**.</span></span>
3. <span data-ttu-id="74ace-178">이전에 만든 이름을 사용 하 여 보고서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-178">Find the report using the name you created earlier.</span></span>
4. <span data-ttu-id="74ace-179">이 보고서를 마우스 오른쪽 단추로 클릭 하 고 **실행**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-179">Right-click this report, and select **Run**.</span></span>
5. <span data-ttu-id="74ace-180">대화 상자가 열리면 **내보내기를** 선택한 다음 **CSV로 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-180">In the dialog that opens, select **Export** and then select **Save as CSV**.</span></span>
6. <span data-ttu-id="74ace-181">이 보고서 버전은 Configuration Manager가 통신 하는 모든 Windows 10 장치에서 해시를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-181">This version of report extracts hashes from all Windows 10 devices that Configuration Manager communicates with.</span></span> <span data-ttu-id="74ace-182">Microsoft Managed Desktop에 등록할 장치에만 결과를 필터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-182">You will need to filter results to just those devices you plan to register with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="74ace-183">구성 관리자의 쿼리는 내보낸 열 이름에 공백을 사용할 수 없습니다. 이러한 이유는 "Serial_Number" 및 "HardwareHash"를 입력 하는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-183">The query in Configuration Manager doesn’t allow spaces in exported column names; that's why the steps had you enter "Serial_Number" and "HardwareHash."</span></span> <span data-ttu-id="74ace-184">내보낸 CSV 파일이 있으므로 여기에 표시 된 것 처럼 *일련 번호* 및 *하드웨어 해시* 를 읽도록 보고서 헤더를 편집 해야 device registration을 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-184">Now that you have the exported CSV file, you must edit the report headers to read *Serial Number* and *Hardware Hash* as shown here before you proceed with device registration.</span></span>

<span data-ttu-id="74ace-185">이제 [Azure Portal을 사용 하 여 장치 등록](#register-devices-by-using-the-azure-portal)을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-185">Now you can proceed to [Register devices by using the Azure Portal](#register-devices-by-using-the-azure-portal).</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="74ace-186">Active Directory PowerShell 스크립트 메서드</span><span class="sxs-lookup"><span data-stu-id="74ace-186">Active Directory PowerShell script method</span></span>

<span data-ttu-id="74ace-187">Active Directory 환경에서는 `Get-MMDRegistrationInfo` PowerShell cmdlet을 사용 하 여 WinRM을 사용 하 여 Active Directory 그룹의 장치에서 정보를 원격으로 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-187">In an Active Directory environment, you can use the `Get-MMDRegistrationInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="74ace-188">또한이 `Get-AD Computer` cmdlet을 사용 하 여 카탈로그에 포함 된 특정 하드웨어 모델 이름에 대 한 필터링 된 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-188">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="74ace-189">이 작업을 수행 하려면 먼저 다음 필수 구성 요소를 확인 한 다음 단계를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-189">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="74ace-190">WinRM을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-190">WinRM is enabled.</span></span>
- <span data-ttu-id="74ace-191">등록 하려는 장치가 네트워크에서 활성 상태 (즉, 연결이 끊어지거나 꺼져 있지 않음)입니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-191">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="74ace-192">장치에서 원격으로 실행할 수 있는 권한이 있는 도메인 자격 증명 매개 변수가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-192">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="74ace-193">Windows 방화벽에서 WMI 액세스를 허용 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-193">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="74ace-194">이 작업을 수행 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-194">To do that, follow these steps:</span></span>
    1. <span data-ttu-id="74ace-195">**Windows Defender 방화벽** 제어판을 열고 **windows defender 방화벽을 통해 앱 또는 기능 허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-195">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    2. <span data-ttu-id="74ace-196">목록에서 **WMI (Windows Management Instrumentation)** 를 찾고 **개인 및 공용**모두에 대해이 기능을 사용 하도록 설정 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-196">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="74ace-197">관리 권한으로 PowerShell 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-197">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="74ace-198">다음 스크립트 중 *하나* 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-198">Run *either one* of these scripts:</span></span>
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. <span data-ttu-id="74ace-199">장치에 대 한 항목이 있을 수 있는 모든 디렉터리에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-199">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="74ace-200">Windows Server Active Directory 도메인 서비스 및 Azure Active Directory를 포함 하 여 *모든* 디렉터리에서 각 장치에 대 한 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-200">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="74ace-201">이 제거 작업을 완료 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-201">Be aware that this removal could take a few hours to completely process.</span></span>
4. <span data-ttu-id="74ace-202">장치에 대 한 항목이 있을 수 있는 관리 서비스에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-202">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="74ace-203">Microsoft 끝점 구성 관리자, Microsoft Intune 및 Windows Autopilot를 비롯 한 *모든* 관리 서비스에서 각 장치에 대 한 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-203">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manger, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="74ace-204">이 제거 작업을 완료 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-204">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="74ace-205">이제 [장치 등록](#register-devices)을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-205">Now you can proceed to [register devices](#register-devices).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="74ace-206">PowerShell 수동 스크립트 방법</span><span class="sxs-lookup"><span data-stu-id="74ace-206">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="74ace-207">관리 권한으로 PowerShell 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-207">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="74ace-208">실행`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="74ace-208">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="74ace-209">실행`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="74ace-209">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="74ace-210">해시 데이터를 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-210">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="74ace-211">Flash drive 메서드</span><span class="sxs-lookup"><span data-stu-id="74ace-211">Flash drive method</span></span>

1. <span data-ttu-id="74ace-212">등록 중인 장치 이외의 디바이스에서 USB 드라이브를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-212">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="74ace-213">관리 권한으로 PowerShell 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-213">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="74ace-214">실행`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="74ace-214">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="74ace-215">등록 중인 디바이스를 켜면 *설치 환경이 시작 되지*않습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-215">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="74ace-216">실수로 설치 환경을 시작한 경우 장치를 초기화 하거나 다시 이미지로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-216">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="74ace-217">USB 드라이브를 삽입 한 다음 SHIFT + F10 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-217">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="74ace-218">관리 권한으로 PowerShell 프롬프트를 열고를 실행 `cd <pathToUsb>`합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-218">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="74ace-219">실행`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="74ace-219">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="74ace-220">실행`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="74ace-220">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="74ace-221">USB 드라이브를 제거한 다음 다음을 실행 하 여 장치를 종료 합니다.`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="74ace-221">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="74ace-222">해시 데이터를 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-222">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="74ace-223">등록을 완료 한 후 다시 등록할 때까지 디바이스에 전원을 공급 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="74ace-223">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="74ace-224">해시 데이터 병합</span><span class="sxs-lookup"><span data-stu-id="74ace-224">Merge hash data</span></span>

<span data-ttu-id="74ace-225">수동 PowerShell 또는 플래시 드라이브 방법으로 하드웨어 해시 데이터를 수집한 경우에는 CSV 파일의 데이터를 단일 파일로 결합 하 여 등록을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-225">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="74ace-226">다음과 같은 샘플 PowerShell 스크립트를 통해이를 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-226">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

<span data-ttu-id="74ace-227">해시 데이터를 하나의 CSV 파일에 병합 하 여 이제 [장치 등록](#register-devices)을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-227">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices).</span></span>

### <a name="register-devices"></a><span data-ttu-id="74ace-228">장치 등록</span><span class="sxs-lookup"><span data-stu-id="74ace-228">Register devices</span></span>

<span data-ttu-id="74ace-229">등록 하려면 CSV 파일을 특정 형식으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-229">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="74ace-230">이전 단계에서 데이터를 직접 수집한 경우 파일은 올바른 형식으로 되어 있어야 합니다. 공급자 로부터 파일을 가져오는 경우에는 형식을 조정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-230">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="74ace-231">편의상이 CSV 파일의 [서식 파일](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) 을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-231">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="74ace-232">샘플 1과 **정확히 같은 열 머리글** 을 포함 해야 하지만 (제조업체, 모델 등), 다른 행에 대 한 고유한 데이터를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-232">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="74ace-233">서식 파일을 사용 하는 경우 메모장 등의 텍스트 편집 도구에서이 템플릿을 열고 행 2와 아래에 데이터만 입력 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-233">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="74ace-234">예제 데이터를 변경 하는 것을 잊은 경우에는 등록이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-234">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="74ace-235">Azure Portal을 사용 하 여 장치 등록</span><span class="sxs-lookup"><span data-stu-id="74ace-235">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="74ace-236">Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal)의 왼쪽 탐색 창에서 **장치** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-236">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="74ace-237">**+ 장치 등록**을 선택 합니다. 날아오기는 다음과 같이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-237">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="74ace-238">[![등록 장치를 선택한 후 날아오기, 할당 된 사용자, 일련 번호, 상태, 마지막으로 표시 된 날짜 및 연령에 해당 하는 열이 있는 장치 나열](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="74ace-238">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (Sadly이는 그렇지 않습니다. 이 노트를 제거할 수는 있지만,이 정보를 다시 한 번에 채팅할 때까지 계속 남아 있습니다.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="74ace-240">다음 단계를 따릅니다:</span><span class="sxs-lookup"><span data-stu-id="74ace-240">Follow these steps:</span></span>

1. <span data-ttu-id="74ace-241">**파일 업로드**에서 이전에 만든 CSV 파일의 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-241">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="74ace-242">원하는 경우 사용자의 추적 목적으로 **주문 id** 또는 **구매 ID** 를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-242">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="74ace-243">이러한 값에 대 한 형식 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-243">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="74ace-244">**장치 등록**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-244">Select **Register devices**.</span></span> <span data-ttu-id="74ace-245">시스템은 장치를 디바이스 **블레이드에서**장치 목록에 추가 하 고 **등록 보류 중**으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-245">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="74ace-246">등록은 일반적으로 10 분 미만이 걸리고, 성공적인 장치는 **사용자가** 사용할 준비가 된 것으로 표시 되 고 최종 사용자가 사용을 시작할 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-246">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="74ace-247">기본 **Microsoft Managed Desktop-Devices** 페이지에서 장치 등록의 진행 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-247">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="74ace-248">다음과 같은 가능한 상태가 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-248">Possible states reported there include:</span></span>

| <span data-ttu-id="74ace-249">시/도</span><span class="sxs-lookup"><span data-stu-id="74ace-249">State</span></span> | <span data-ttu-id="74ace-250">설명</span><span class="sxs-lookup"><span data-stu-id="74ace-250">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="74ace-251">등록 보류 중</span><span class="sxs-lookup"><span data-stu-id="74ace-251">Registration pending</span></span> | <span data-ttu-id="74ace-252">등록이 아직 완료 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-252">Registration is not done yet.</span></span> <span data-ttu-id="74ace-253">나중에 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-253">Check back later.</span></span> |
| <span data-ttu-id="74ace-254">등록 실패</span><span class="sxs-lookup"><span data-stu-id="74ace-254">Registration failed</span></span> | <span data-ttu-id="74ace-255">등록을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-255">Registration could not be completed.</span></span> <span data-ttu-id="74ace-256">자세한 내용은 [장치 등록 문제 해결](#troubleshooting-device-registration) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74ace-256">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="74ace-257">사용자 준비</span><span class="sxs-lookup"><span data-stu-id="74ace-257">Ready for user</span></span> | <span data-ttu-id="74ace-258">등록을 완료 했으며 이제 장치를 최종 사용자에 게 배달할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-258">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="74ace-259">Microsoft Managed Desktop은 처음 설정할 때 가이드를 제공 하므로 추가 준비를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-259">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="74ace-260">활성</span><span class="sxs-lookup"><span data-stu-id="74ace-260">Active</span></span> | <span data-ttu-id="74ace-261">장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-261">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="74ace-262">또한 장치를 정기적으로 사용 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-262">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="74ace-263">있었던</span><span class="sxs-lookup"><span data-stu-id="74ace-263">Inactive</span></span> | <span data-ttu-id="74ace-264">장치가 최종 사용자에 게 배달 되었으며 테 넌 트에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-264">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="74ace-265">그러나 최근에 최근 7 일 이내에 장치를 사용 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-265">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="74ace-266">장치 등록 문제 해결</span><span class="sxs-lookup"><span data-stu-id="74ace-266">Troubleshooting device registration</span></span>

| <span data-ttu-id="74ace-267">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="74ace-267">Error message</span></span> | <span data-ttu-id="74ace-268">세부 정보</span><span class="sxs-lookup"><span data-stu-id="74ace-268">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="74ace-269">장치를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="74ace-269">Device not found</span></span> | <span data-ttu-id="74ace-270">제공 된 제조업체, 모델 또는 일련 번호에 대해 일치 하는 항목을 찾을 수 없기 때문에이 장치를 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-270">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="74ace-271">장치 공급자에서 이러한 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-271">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="74ace-272">하드웨어 해시가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-272">Hardware hash not valid</span></span> | <span data-ttu-id="74ace-273">이 장치에 대해 제공한 하드웨어 해시가 올바르게 포맷 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-273">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="74ace-274">하드웨어 해시를 두 번 확인 한 다음 다시 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-274">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="74ace-275">장치가 이미 등록 됨</span><span class="sxs-lookup"><span data-stu-id="74ace-275">Device already registered</span></span> | <span data-ttu-id="74ace-276">이 장치는 이미 조직에 등록 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-276">This device is already registered to your organization.</span></span> <span data-ttu-id="74ace-277">추가 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-277">No further action required.</span></span> |
| <span data-ttu-id="74ace-278">다른 조직에서 요구 하는 장치</span><span class="sxs-lookup"><span data-stu-id="74ace-278">Device claimed by another organization</span></span> | <span data-ttu-id="74ace-279">이 장치는 다른 조직에서 이미 요구 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-279">This device has already been claimed by another organization.</span></span> <span data-ttu-id="74ace-280">장치 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="74ace-280">Check with your device supplier.</span></span> |
| <span data-ttu-id="74ace-281">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="74ace-281">Unexpected error</span></span> | <span data-ttu-id="74ace-282">요청을 자동으로 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-282">Your request could not be automatically processed.</span></span> <span data-ttu-id="74ace-283">지원 서비스에 문의 하 여 요청 ID를 제공 합니다.<requestId></span><span class="sxs-lookup"><span data-stu-id="74ace-283">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="74ace-284">이미지 확인</span><span class="sxs-lookup"><span data-stu-id="74ace-284">Check the image</span></span>

<span data-ttu-id="74ace-285">장치가 Microsoft 관리 되는 데스크톱 파트너 공급자 로부터 온 것 이라면 이미지가 정확 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-285">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="74ace-286">원하는 경우 이미지를 직접 적용 하는 것도 환영 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-286">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="74ace-287">시작 하려면 사용 중인 Microsoft 담당자에 게 문의 하 여 이미지를 적용할 위치와 단계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-287">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="74ace-288">장치 배달</span><span class="sxs-lookup"><span data-stu-id="74ace-288">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74ace-289">사용자에 게 디바이스를 전달 하기 전에 해당 사용자에 대 한 [적절 한 라이선스](../get-ready/prerequisites.md) 를 확보 하 고 적용 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-289">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="74ace-290">모든 라이선스가 적용 되 면 [사용자가 장치를 사용할 준비가](get-started-devices.md)되 면 사용자가 장치를 시작 하 고 Windows 설치 환경을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ace-290">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









