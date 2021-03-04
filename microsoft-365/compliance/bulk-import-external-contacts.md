---
title: Exchange Online으로 외부 연락처 대량 가져오기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: 관리자가 Exchange Online PowerShell 및 CSV 파일을 사용하여 외부 연락처를 전체 주소 목록으로 대량으로 가져오는 방법을 알아보습니다.
ms.openlocfilehash: 475afc3b0622c404b50ebe5549bb5be85af80c5e
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423255"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="71fed-103">Exchange Online으로 외부 연락처 대량 가져오기</span><span class="sxs-lookup"><span data-stu-id="71fed-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="71fed-104">**이 문서는 관리자를 위한 것입니다. 자신의 사서함으로 연락처를 가져오려고 하나요? Outlook으로 [연락처 가져오기 참조](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="71fed-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="71fed-105">회사에 Exchange Online의 공유 주소 목록(전체 주소 목록이라고도 하는)에 포함할 기존 비즈니스 연락처가 많이 있나요?</span><span class="sxs-lookup"><span data-stu-id="71fed-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="71fed-106">회사 내부의 사용자와 마찬가지로 외부 연락처를 메일 그룹의 구성원으로 추가하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="71fed-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="71fed-107">이 경우 Exchange Online PowerShell 및 CSV(콤보로 구분된 값) 파일을 사용하여 외부 연락처를 Exchange Online으로 대량으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-107">If so, you can use Exchange Online PowerShell and a CSV (comma-separated value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="71fed-108">3단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="71fed-109">1단계: 외부 연락처에 대한 정보가 포함된 CSV 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="71fed-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="71fed-110">2단계: PowerShell을 사용하여 외부 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="71fed-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="71fed-111">3단계: 외부 연락처의 속성에 정보 추가</span><span class="sxs-lookup"><span data-stu-id="71fed-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="71fed-112">이러한 단계를 완료하여 연락처를 가져온 후 다음 추가 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="71fed-113">외부 연락처 추가</span><span class="sxs-lookup"><span data-stu-id="71fed-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="71fed-114">공유 주소 책에서 외부 연락처 숨기기</span><span class="sxs-lookup"><span data-stu-id="71fed-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="71fed-115">1단계: 외부 연락처에 대한 정보가 포함된 CSV 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="71fed-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="71fed-116">첫 번째 단계는 Exchange Online으로 가져올 각 외부 연락처에 대한 정보가 포함된 CSV 파일을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="71fed-117">다음 텍스트를 메모장의 텍스트 파일에 복사하고 파일 이름 접미사 .csv를 사용하여 바탕 화면에 CSV 파일로 저장합니다. 예를 들어 ExternalContacts.csv.</span><span class="sxs-lookup"><span data-stu-id="71fed-117">Copy the following text to a text file in NotePad, and save it on your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="71fed-118">언어에 특수 문자(예: **å,** **ä**, **ö)가** 포함되어 있는 경우 메모장에 파일을 저장할 때 CSV 파일을 UTF-8 또는 기타 유니코드 인코딩으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    <span data-ttu-id="71fed-119">CSV 파일의 첫 번째 행 또는 머리글 행에는 Exchange Online으로 가져올 때 사용할 수 있는 연락처의 속성이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="71fed-120">각 속성 이름은 콤보로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="71fed-121">머리줄 행 아래에 있는 각 행은 단일 외부 연락처를 가져오기 위한 속성 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="71fed-122">이 텍스트에는 삭제할 수 있는 예제 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="71fed-123">그러나 첫 번째(헤더) 행은 삭제하거나 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="71fed-124">외부 연락처의 모든 속성이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="71fed-125">Excel을 사용하여 CSV 파일을 편집하는 것이 훨씬 더 쉬우기 때문에 Microsoft Excel에서 CSV 파일을 열고 CSV 파일을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="71fed-126">Exchange Online으로 가져올 각 연락처에 대한 행을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="71fed-127">가능한 한 많은 셀을 채우십시오.</span><span class="sxs-lookup"><span data-stu-id="71fed-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="71fed-128">이 정보는 각 연락처의 공유 주소장에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="71fed-129">외부 연락처를 만들 때 외부 연락처를 만드는 데 필요한 속성(헤더 행의 처음 4개 항목)은 CSV 파일에 채워야 합니다. **ExternalEmailAddress,** **Name,** **FirstName,** **LastName**.</span><span class="sxs-lookup"><span data-stu-id="71fed-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="71fed-130">2단계에서 실행한 PowerShell 명령은 이러한 속성의 값을 사용하여 연락처를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="71fed-131">2단계: PowerShell을 사용하여 외부 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="71fed-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="71fed-132">다음 단계는 1단계 및 PowerShell에서 만든 CSV 파일을 사용하여 CSV 파일에 나열된 외부 연락처를 Exchange Online으로 대량으로 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="71fed-133">PowerShell을 Exchange Online 조직에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="71fed-134">단계별 지침은 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="71fed-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="71fed-135">Exchange Online PowerShell에 연결할 때 전역 관리자 계정의 사용자 이름과 암호를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="71fed-135">Be sure to use the user name and password for your global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="71fed-136">PowerShell을 Exchange Online에 연결한 후 1단계에서 CSV 파일을 저장한 데스크톱 폴더로 이동합니다. 예를 들면 `C:\Users\Administrator\desktop` 입니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="71fed-137">다음 명령을 실행하여 외부 연락처를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-137">Run the following command to create the external contacts:</span></span>

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="71fed-138">가져오는 연락처 수에 따라 새 연락처를 만드는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="71fed-139">명령 실행이 완료되면 PowerShell에 만들어진 새 연락처의 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="71fed-140">새 외부 연락처를 보려면 EAC(Exchange 관리 센터)로 이동한 다음 받는 사람 연락처  \> **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="71fed-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="71fed-141">EAC에 연결하는 방법에 대한 지침은 [Exchange Online의 Exchange 관리 센터를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=328197)</span><span class="sxs-lookup"><span data-stu-id="71fed-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="71fed-142">필요한 경우 새로 **고침을** 클릭하여 목록을 업데이트하고 가져온 외부 연락처를 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-142">If necessary, click **Refresh** to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="71fed-143">가져온 연락처는 Outlook 및 웹에서 Outlook의 공유 주소 책에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="71fed-144">사용자 연락처로 가면 Microsoft 365 관리 센터에서 **연락처를 볼** \> **수도 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="71fed-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="71fed-145">3단계: 외부 연락처의 속성에 정보 추가</span><span class="sxs-lookup"><span data-stu-id="71fed-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="71fed-146">2단계에서 명령을 실행하면 외부 연락처가 만들어지지만 CSV 파일에 있는 대부분의 셀의 정보인 연락처나 조직 정보는 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from most of the cells in the CSV file.</span></span> <span data-ttu-id="71fed-147">이는 새 외부 연락처를 만들 때 필요한 속성만 채워지기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="71fed-148">CSV 파일에 정보가 모두 채워지는 경우 걱정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="71fed-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="71fed-149">여기에 없는 경우 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="71fed-150">PowerShell을 Exchange Online 조직에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="71fed-151">단계별 지침은 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="71fed-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="71fed-152">1단계에서 CSV 파일을 저장한 데스크톱 폴더로 이동합니다. 예를 들면 `C:\Users\Administrator\desktop` 입니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-152">Go to the desktop folder where you saved the CSV file in Step 1; for example, `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="71fed-153">다음 두 명령을 실행하여 CSV 파일의 다른 속성을 2단계에서 만든 외부 연락처에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="71fed-154">Manager  _매개_ 변수에 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="71fed-155">CSV 파일에 셀이 비어 있는 경우 오류가 발생하고 연락처에 속성 정보가 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="71fed-156">관리자를 지정할 필요가 없는 경우 이전 PowerShell 명령에서  ` -Manager $_.Manager ` 삭제하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="71fed-157">1단계에서 가져온 수에 따라 연락처를 업데이트하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="71fed-158">속성이 연락처에 추가 는 확인:</span><span class="sxs-lookup"><span data-stu-id="71fed-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="71fed-159">EAC에서 **받는 사람** \> **연락처** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="71fed-160">연락처를 클릭한 다음 편집 **편집** ![ 아이콘을 ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 클릭하여 연락처의 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-160">Click a contact and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="71fed-161">모두 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-161">That's it!</span></span> <span data-ttu-id="71fed-162">사용자는 주소 책 Outlook 및 웹에서 Outlook에서 연락처와 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="71fed-163">외부 연락처 추가</span><span class="sxs-lookup"><span data-stu-id="71fed-163">Add more external contacts</span></span>

<span data-ttu-id="71fed-164">1~3단계를 반복하여 Exchange Online에 새 외부 연락처를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="71fed-165">사용자 또는 회사의 사용자는 새 연락처의 CSV 파일에 새 행을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="71fed-166">그런 다음 2단계 및 3단계의 PowerShell 명령을 실행하여 새 연락처에 정보를 만들고 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71fed-167">명령을 실행하여 새 연락처를 만들면 앞에서 만든 연락처가 이미 존재하다는 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="71fed-168">그러나 CSV 파일에 추가된 새 연락처가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="71fed-169">공유 주소장에서 외부 연락처 숨기기></span><span class="sxs-lookup"><span data-stu-id="71fed-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="71fed-170">일부 회사에서는 외부 연락처만 사용하여 메일 그룹의 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="71fed-171">이 시나리오에서는 공유 주소 책에서 외부 연락처를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="71fed-172">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-172">Here's how:</span></span>
  
1.  <span data-ttu-id="71fed-173">PowerShell을 Exchange Online 조직에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="71fed-174">단계별 지침은 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="71fed-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="71fed-175">단일 외부 연락처를 숨기기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-175">To hide a single external contact, run the following command.</span></span>
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    <span data-ttu-id="71fed-176">예를 들어 공유 주소 책에서 Pilar Pinilla를 숨기기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. <span data-ttu-id="71fed-177">공유 주소 책에서 모든 외부 연락처를 숨기기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="71fed-178">외부 연락처를 숨기면 외부 연락처가 공유 주소장에 표시되지 않지만 메일 그룹의 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71fed-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
