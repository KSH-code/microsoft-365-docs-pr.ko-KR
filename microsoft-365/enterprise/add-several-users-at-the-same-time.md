---
title: Microsoft 365에 여러 사용자를 동시에 추가-관리자 도움말
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
ms.assetid: 1f5767ed-e717-4f24-969c-6ea9d412ca88
description: '스프레드시트나 기타 CSV 파일의 목록에서 비즈니스용 Microsoft 365에 여러 사용자를 추가 하는 방법에 대해 알아봅니다. Microsoft 365에 계정을 추가 하는 방법을 설명 하는 YouTube의 비디오를 시청 하세요. 이 프로세스가 끝나면 계정이 있는 각 사용자에 게 Microsoft 365 사서함이 포함 됩니다. '
ms.openlocfilehash: a970fbfa28214543e34011f1310742c6fb811d09
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071516"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a><span data-ttu-id="c2522-105">Microsoft 365에 여러 사용자를 동시에 추가-관리자 도움말</span><span class="sxs-lookup"><span data-stu-id="c2522-105">Add several users at the same time to Microsoft 365 - Admin Help</span></span>

<span data-ttu-id="c2522-p102">팀의 각 사용자는 전자 메일 및 Office와 같은 Microsoft 365 서비스에 로그인 하 고 액세스할 수 있으려면 먼저 사용자 계정을 사용 해야 합니다. 사용자가 많은 경우 Excel 스프레드시트 또는 CSV 형식으로 저장 된 다른 파일에서 모든 계정을 한 번에 추가할 수 있습니다. [CSV 형식이 무엇 인지 알 수 없습니까?](add-several-users-at-the-same-time.md#__toc316652088)</span><span class="sxs-lookup"><span data-stu-id="c2522-p102">Each person on your team needs a user account before they can sign in and access Microsoft 365 services, such as email and Office. If you have a lot of people, you can add their accounts all at once from an Excel spreadsheet or other file saved in CSV format. [Not sure what CSV format is?](add-several-users-at-the-same-time.md#__toc316652088)</span></span>
  
> [!NOTE] 
> <span data-ttu-id="c2522-109">새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a><span data-ttu-id="c2522-110">Microsoft 365 관리 센터에서 여러 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="c2522-110">Add multiple users in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="c2522-111">회사 또는 학교 계정으로 Microsoft 365에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-111">Sign in to Microsoft 365 with your work or school account.</span></span> 
    
2. <span data-ttu-id="c2522-112">관리 센터에서 **사용자** \> **활성 사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-112">In the admin center, choose **Users** \> **Active users**.</span></span>

3. <span data-ttu-id="c2522-113">**여러 사용자 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-113">Select **Add multiple users**.</span></span>

4. <span data-ttu-id="c2522-114">
            **여러 사용자 가져오기\*\* 패널에서 예제 데이터가 입력되어 있는 예제 CSV 파일과 입력되어 있지 않은 예제 CSV 파일 중 선택하여 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-114">On the **Import multiple users** panel, you can optionally download a sample CSV file with or without sample data filled in.</span></span> 
    
    <span data-ttu-id="c2522-115">스프레드시트에 예제 1과 **정확히 같은 열 머리글이** 포함 되어야 합니다 (사용자 이름, 이름 등).</span><span class="sxs-lookup"><span data-stu-id="c2522-115">Your spreadsheet needs to include the **exact same column headings** as the sample one (User Name, First Name, and so on).</span></span> <span data-ttu-id="c2522-116">서식 파일을 사용 하는 경우 메모장과 같은 텍스트 편집 도구에서 연 다음 모든 데이터를 행 1로 그대로 유지 하 고 행 2와 아래에 데이터만 입력 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-116">If you use the template, open it in a text editing tool, like Notepad, and consider leaving all the data in row 1 alone, and only entering data in rows 2 and below.</span></span> 
    
    <span data-ttu-id="c2522-117">스프레드시트는 사용자 이름(예: hyunki@contoso.com)과 각 사용자에 대한 표시 이름(예: 유현기)에 대한 값도 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-117">Your spreadsheet also needs to include values for the user name (like bob@contoso.com) and a display name (like Bob Kelly) for each user.</span></span> 
    
  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. <span data-ttu-id="c2522-118">상자에 파일 경로를 입력하거나 **찾아보기** 를 선택하여 CSV 파일의 위치를 찾은 다음 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-118">Enter a file path into the box, or choose **Browse** to browse to the CSV file location, then choose **Verify**.</span></span>
  
    <span data-ttu-id="c2522-p104">파일에 문제가 있는 경우에는 문제가 창에 표시됩니다. 로그 파일을 다운로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-p104">If there are problems with the file, the problem is displayed in the panel. You can also download a log file.</span></span>
    
5. <span data-ttu-id="c2522-121">
            \*\*Set user options\*\* (사용자 옵션 설정) 대화 상자에서는 로그인 상태를 설정하고 모든 사용자에게 할당할 제품 라이선스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-121">On the **Set user options** dialog you can set the sign-in status and choose the product license that will be assigned to all users.</span></span> 
    
6. <span data-ttu-id="c2522-122">
            \*\*View your result\*\* (결과 보기) 대화 상자에서는 결과를 자신이나 다른 사용자(암호는 일반 텍스트가 됨)에 보내도록 선택할 수 있으며, 만들어진 사용자의 수와 새 사용자에게 할당하기 위해 추가 라이선스를 구입해야 하는지를 알 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-122">On the **View your result** dialog you can choose to send the results to either yourself or other users (passwords will be in plain text) and you can see how many users were created, and if you need to purchase more licenses to assign to some of the new users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="c2522-123">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c2522-123">Next steps</span></span>
<span data-ttu-id="c2522-124"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c2522-124"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="c2522-125">이러한 사용자는 이제 [PC 또는 Mac에서 Microsoft 365 또는 Office 2016을 다운로드 하 고 설치 하거나 다시](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-125">Now that these people have accounts, they need to [Download and install or reinstall Microsoft 365 or Office 2016 on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> <span data-ttu-id="c2522-126">팀의 각 사용자는 최대 5 대의 Pc 또는 Mac에 Microsoft 365을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-126">Each person on your team can install Microsoft 365 on up to 5 PCs or Macs.</span></span> 
    
- <span data-ttu-id="c2522-127">각 사용자는 iPhones, iPads 및 Android 휴대폰 및 태블릿과 같은 최대 5대의 태블릿과 5대의 휴대폰에서 [모바일 장치의 Office 앱 및 전자 메일을 설정](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-127">Each person can also [Set up Office apps and email on a mobile device](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) on up to 5 tablets and 5 phones, such as iPhones, iPads, and Android phones and tablets.</span></span> <span data-ttu-id="c2522-128">이 방법으로 어디서나 Office 파일을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-128">This way they can edit Office files from anywhere.</span></span> 
    
    <span data-ttu-id="c2522-129">설치 단계에 대 한 종단 간 목록을 보려면 [Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2522-129">See [Set up Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) for an end-to-end list of the setup steps.</span></span> 
    
## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a><span data-ttu-id="c2522-130">Microsoft 365에 사용자를 추가 하는 방법에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="c2522-130">More information about how to add users to Microsoft 365</span></span>
<span data-ttu-id="c2522-131"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c2522-131"><a name="bk_preview"> </a></span></span>

### <a name="not-sure-what-csv-format-is"></a><span data-ttu-id="c2522-132">CSV 형식이란?</span><span class="sxs-lookup"><span data-stu-id="c2522-132">Not sure what CSV format is?</span></span>
<span data-ttu-id="c2522-133"><a name="__toc316652088"> </a></span><span class="sxs-lookup"><span data-stu-id="c2522-133"><a name="__toc316652088"> </a></span></span>

<span data-ttu-id="c2522-p107">CSV 파일은 쉼표로 구분된 값을 사용한 파일입니다. 모든 텍스트 편집기나 Excel과 같은 스프레드시트 프로그램에서 이와 같은 파일을 만들거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-p107">A CSV file is a file with comma separated values. You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.</span></span>
  
<span data-ttu-id="c2522-136">시작점으로 [이 예제 스프레드시트](https://www.microsoft.com/download/details.aspx?id=45485)를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-136">You can download [this sample spreadsheet](https://www.microsoft.com/download/details.aspx?id=45485) as a starting point.</span></span> <span data-ttu-id="c2522-137">Microsoft 365에서는 첫 번째 행에 열 머리글이 필요 하므로 다른 항목으로 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-137">Remember that Microsoft 365 requires column headings in the first row so don't replace them with something else.</span></span> 
  
<span data-ttu-id="c2522-138">파일을 새 이름으로 저장하고 CSV 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-138">Save the file with a new name, and specify CSV format.</span></span>
  
![Excel CSV 형식으로 파일을 저장하는 방법 이미지](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
<span data-ttu-id="c2522-p109">파일을 저장할 때 파일을 CSV 형식으로 저장하면 통합 문서의 일부 기능이 손실된다는 메시지가 표시될 수 있지만 괜찮습니다. **예** 를 클릭하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-p109">When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format. This is okay. Click **Yes** to continue.</span></span> 
  
![Excel에서 파일을 정말로 CSV 형식으로 저장할지 묻는 메시지 그림](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a><span data-ttu-id="c2522-144">스프레드시트 서식 지정 팁</span><span class="sxs-lookup"><span data-stu-id="c2522-144">Tips for formatting your spreadsheet</span></span>
<span data-ttu-id="c2522-145"><a name="__toc314595848"> </a></span><span class="sxs-lookup"><span data-stu-id="c2522-145"><a name="__toc314595848"> </a></span></span>

- <span data-ttu-id="c2522-146">**예제 스프레드시트와 같은 열 머리글이 필요한가요?**</span><span class="sxs-lookup"><span data-stu-id="c2522-146">**Do I need the same column headings as in the sample spreadsheet?**</span></span> <span data-ttu-id="c2522-147">예.</span><span class="sxs-lookup"><span data-stu-id="c2522-147">Yes.</span></span> <span data-ttu-id="c2522-148">예제 스프레드시트에는 첫 행에 열 머리글이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-148">The sample spreadsheet contains column headings in the first row.</span></span> <span data-ttu-id="c2522-149">해당 머리글은 필수 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-149">These headings are required.</span></span> <span data-ttu-id="c2522-150">Microsoft 365에 추가 하려는 각 사용자에 대해 머리글 아래에 행을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-150">For each user you want to add to Microsoft 365, create a row under the heading.</span></span> <span data-ttu-id="c2522-151">열 머리글을 추가, 변경 또는 삭제 하면 Microsoft 365에서 해당 파일의 정보를 사용자에 게 만들지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-151">If you add, change, or delete any of the column headings, Microsoft 365 might not be able to create users from the information in the file.</span></span> 
    
- <span data-ttu-id="c2522-p111">**각 사용자에 대해 필요한 정보가 일부만 있는 경우** 사용자 이름 및 표시 이름은 필수 항목입니다. 이 정보 없이는 새 사용자를 추가할 수 없습니다. 팩스 등 기타 정보가 없는 경우 공백과 쉼표를 사용해 필드를 빈 상태로 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-p111">**What if I don't have all the information required for each user?** The user name and display name are required, and you cannot add a new user without this information. If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.</span></span> 
    
- <span data-ttu-id="c2522-155">**스프레드시트의 크기는 얼마나 작거나 클 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="c2522-155">**How small or large can the spreadsheet be?**</span></span> <span data-ttu-id="c2522-156">스프레드시트에는 행이 두 개 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-156">The spreadsheet must have at least two rows.</span></span> <span data-ttu-id="c2522-157">One is for the column headings (the user data column label) and one for the user.</span><span class="sxs-lookup"><span data-stu-id="c2522-157">One is for the column headings (the user data column label) and one for the user.</span></span> <span data-ttu-id="c2522-158">You cannot have more than 251 rows.</span><span class="sxs-lookup"><span data-stu-id="c2522-158">You cannot have more than 251 rows.</span></span> <span data-ttu-id="c2522-159">If you need to import more than 250 users, you can create more than one spreadsheet.</span><span class="sxs-lookup"><span data-stu-id="c2522-159">If you need to import more than 250 users, you can create more than one spreadsheet.</span></span> 
    
- <span data-ttu-id="c2522-160">**사용할 수 있는 언어**</span><span class="sxs-lookup"><span data-stu-id="c2522-160">**What languages can I use?**</span></span> <span data-ttu-id="c2522-161">스프레드시트를 만들 때 모든 언어나 문자에 사용자 데이터 열 레이블을 입력할 수 있지만 예제에 표시 된 대로 레이블 순서를 변경 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-161">When you create your spreadsheet, you can enter user data column labels in any language or characters, but you must not change the order of the labels, as shown in the sample.</span></span> <span data-ttu-id="c2522-162">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span><span class="sxs-lookup"><span data-stu-id="c2522-162">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span></span> 
    
- <span data-ttu-id="c2522-p114">**다른 국가나 지역의 사용자를 추가하는 경우** 각 지역에 대해 별도의 스프레드시트를 만듭니다. 각 스프레드시트의 사용자 일괄 추가 마법사를 단계적으로 따르면 작업 중인 파일에 포함된 모든 사용자를 한 곳에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-p114">**What if I'm adding users from different countries or regions?** Create a separate spreadsheet for each area. You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.</span></span> 
    
- <span data-ttu-id="c2522-p115">**사용할 수 있는 문자 수 제한** 다음 표에서는 예제 스프레드시트의 사용자 데이터 열 레이블 및 최대 문자 길이를 각각 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-p115">**Is there a limit to the number of characters I can use?** The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.</span></span> 
    
|<span data-ttu-id="c2522-168">**사용자 데이터 열 레이블**</span><span class="sxs-lookup"><span data-stu-id="c2522-168">**User data column label**</span></span>|<span data-ttu-id="c2522-169">**최대 문자 길이**</span><span class="sxs-lookup"><span data-stu-id="c2522-169">**Maximum character length**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c2522-170">사용자 이름 (필수)</span><span class="sxs-lookup"><span data-stu-id="c2522-170">User Name (Required)</span></span>  <br/> |<span data-ttu-id="c2522-171">@ 기호를 포함 하는 79는 name@domain 형식으로 되어 \<extension\> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-171">79 including the at sign (@), in the format name@domain.\<extension\>.</span></span> <span data-ttu-id="c2522-172">사용자의 별칭은 50 자를 초과할 수 없으며 도메인 이름은 48 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-172">The user's alias cannot exceed 50 characters, and the domain name cannot exceed 48 characters.</span></span>  <br/> |
|<span data-ttu-id="c2522-173">이름</span><span class="sxs-lookup"><span data-stu-id="c2522-173">First Name</span></span>  <br/> |<span data-ttu-id="c2522-174">64</span><span class="sxs-lookup"><span data-stu-id="c2522-174">64</span></span>  <br/> |
|<span data-ttu-id="c2522-175">성</span><span class="sxs-lookup"><span data-stu-id="c2522-175">Last Name</span></span>  <br/> |<span data-ttu-id="c2522-176">64</span><span class="sxs-lookup"><span data-stu-id="c2522-176">64</span></span>  <br/> |
|<span data-ttu-id="c2522-177">표시 이름 (필수)</span><span class="sxs-lookup"><span data-stu-id="c2522-177">Display Name (required)</span></span>  <br/> |<span data-ttu-id="c2522-178">256</span><span class="sxs-lookup"><span data-stu-id="c2522-178">256</span></span>  <br/> |
|<span data-ttu-id="c2522-179">직함</span><span class="sxs-lookup"><span data-stu-id="c2522-179">Job Title</span></span>  <br/> |<span data-ttu-id="c2522-180">64</span><span class="sxs-lookup"><span data-stu-id="c2522-180">64</span></span>  <br/> |
|<span data-ttu-id="c2522-181">부서</span><span class="sxs-lookup"><span data-stu-id="c2522-181">Department</span></span>  <br/> |<span data-ttu-id="c2522-182">64</span><span class="sxs-lookup"><span data-stu-id="c2522-182">64</span></span>  <br/> |
|<span data-ttu-id="c2522-183">사무실 번호</span><span class="sxs-lookup"><span data-stu-id="c2522-183">Office Number</span></span>  <br/> |<span data-ttu-id="c2522-184">128</span><span class="sxs-lookup"><span data-stu-id="c2522-184">128</span></span>  <br/> |
|<span data-ttu-id="c2522-185">사무실 전화</span><span class="sxs-lookup"><span data-stu-id="c2522-185">Office Phone</span></span>  <br/> |<span data-ttu-id="c2522-186">64</span><span class="sxs-lookup"><span data-stu-id="c2522-186">64</span></span>  <br/> |
|<span data-ttu-id="c2522-187">휴대폰</span><span class="sxs-lookup"><span data-stu-id="c2522-187">Mobile Phone</span></span>  <br/> |<span data-ttu-id="c2522-188">64</span><span class="sxs-lookup"><span data-stu-id="c2522-188">64</span></span>  <br/> |
|<span data-ttu-id="c2522-189">팩스</span><span class="sxs-lookup"><span data-stu-id="c2522-189">Fax</span></span>  <br/> |<span data-ttu-id="c2522-190">64</span><span class="sxs-lookup"><span data-stu-id="c2522-190">64</span></span>  <br/> |
|<span data-ttu-id="c2522-191">주소</span><span class="sxs-lookup"><span data-stu-id="c2522-191">Address</span></span>  <br/> |<span data-ttu-id="c2522-192">1023</span><span class="sxs-lookup"><span data-stu-id="c2522-192">1023</span></span>  <br/> |
|<span data-ttu-id="c2522-193">구/군/시</span><span class="sxs-lookup"><span data-stu-id="c2522-193">City</span></span>  <br/> |<span data-ttu-id="c2522-194">128</span><span class="sxs-lookup"><span data-stu-id="c2522-194">128</span></span>  <br/> |
|<span data-ttu-id="c2522-195">시/도</span><span class="sxs-lookup"><span data-stu-id="c2522-195">State or Province</span></span>  <br/> |<span data-ttu-id="c2522-196">128</span><span class="sxs-lookup"><span data-stu-id="c2522-196">128</span></span>  <br/> |
|<span data-ttu-id="c2522-197">우편 번호</span><span class="sxs-lookup"><span data-stu-id="c2522-197">ZIP or Postal Code</span></span>  <br/> |<span data-ttu-id="c2522-198">40</span><span class="sxs-lookup"><span data-stu-id="c2522-198">40</span></span>  <br/> |
|<span data-ttu-id="c2522-199">국가 또는 지역</span><span class="sxs-lookup"><span data-stu-id="c2522-199">Country or Region</span></span>  <br/> |<span data-ttu-id="c2522-200">128</span><span class="sxs-lookup"><span data-stu-id="c2522-200">128</span></span>  <br/> |
   
### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a><span data-ttu-id="c2522-201">Microsoft 365에 사용자를 추가할 때 여전히 문제가 발생 하나요?</span><span class="sxs-lookup"><span data-stu-id="c2522-201">Still having problems when adding users to Microsoft 365?</span></span>

- <span data-ttu-id="c2522-p117">**스프레드시트 형식이 올바른지 다시 한 번 확인합니다.** 열 머리글이 예제 파일의 머리글과 일치하는지 확인합니다. 문자 길이 규칙을 준수했고 각 필드를 쉼표로 구분했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-p117">**Double-check that the spreadsheet is formatted correctly.** Check the column headings to make sure they match the headings in the sample file. Make sure you're following the rules for character lengths and that each field is separated by a comma.</span></span> 
    
- <span data-ttu-id="c2522-205">**Microsoft 365의 새 사용자가 바로 표시 되지 않으면 몇 분 정도 기다립니다.**</span><span class="sxs-lookup"><span data-stu-id="c2522-205">**If you don't see the new users in Microsoft 365 right away, wait a few minutes.**</span></span> <span data-ttu-id="c2522-206">Microsoft 365의 모든 서비스에서 변경 내용을 적용 하는 데 약간의 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2522-206">It can take a little while for changes to go across all the services in Microsoft 365.</span></span> 
    
## <a name="related-articles"></a><span data-ttu-id="c2522-207">관련 문서</span><span class="sxs-lookup"><span data-stu-id="c2522-207">Related articles</span></span>

[<span data-ttu-id="c2522-208">사용자를 개별적으로 또는 대량으로 Microsoft 365에 추가</span><span class="sxs-lookup"><span data-stu-id="c2522-208">Add users individually or in bulk to Microsoft 365</span></span>](https://docs.microsoft.com/office365/admin/add-users/add-users)




