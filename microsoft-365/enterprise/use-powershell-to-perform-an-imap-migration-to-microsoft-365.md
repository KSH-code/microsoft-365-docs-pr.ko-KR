---
title: PowerShell을 사용하여 Microsoft 365로 IMAP 마이그레이션 수행
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: PowerShell을 사용하여 Microsoft 365로 IMAP(Internet Mail Access Protocol) 마이그레이션을 수행하는 방법을 확인합니다.
ms.openlocfilehash: 67621ecfca7ec323a73b91a530f848dd7571f9b2
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464447"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a><span data-ttu-id="ca85a-103">PowerShell을 사용하여 Microsoft 365로 IMAP 마이그레이션 수행</span><span class="sxs-lookup"><span data-stu-id="ca85a-103">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>

<span data-ttu-id="ca85a-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="ca85a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ca85a-105">Microsoft 365를 배포하는 프로세스의 일부로 IMAP(Internet Mail Access Protocol) 전자 메일 서비스에서 Microsoft 365로 사용자 사서함의 콘텐츠를 마이그레이션하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-105">As part of the process of deploying Microsoft 365, you can choose to migrate the contents of user mailboxes from an Internet Mail Access Protocol (IMAP) email service to Microsoft 365.</span></span> <span data-ttu-id="ca85a-106">이 문서에서는 Exchange Online PowerShell을 사용하는 전자 메일 IMAP 마이그레이션 작업을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-106">This article walks you through the tasks for an email IMAP migration by using Exchange Online PowerShell.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ca85a-107">Exchange 관리 센터를 사용하여 IMAP 마이그레이션을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-107">You can also use the Exchange admin center to perform an IMAP migration.</span></span> <span data-ttu-id="ca85a-108">[IMAP 사서함 마이그레이션을 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=536685)</span><span class="sxs-lookup"><span data-stu-id="ca85a-108">See [Migrate your IMAP mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=536685).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ca85a-109">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="ca85a-109">What do you need to know before you begin?</span></span>

<span data-ttu-id="ca85a-110">이 작업의 예상 완료 시간: 2-5분(마이그레이션 일괄 처리 만들기에 소요되는 시간).</span><span class="sxs-lookup"><span data-stu-id="ca85a-110">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="ca85a-111">마이그레이션 일괄 처리가 시작되면 마이그레이션 기간은 일괄 처리의 사서함 수, 각 사서함의 크기 및 사용 가능한 네트워크 용량에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-111">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="ca85a-112">사서함을 Microsoft 365로 마이그레이션하는 데 걸리는 기간에 영향을 주는 다른 요인에 대한 자세한 내용은 [마이그레이션 성능을 참조하십시오.](https://go.microsoft.com/fwlink/p/?LinkId=275079)</span><span class="sxs-lookup"><span data-stu-id="ca85a-112">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>
  
<span data-ttu-id="ca85a-p104">이 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 필요한 사용 권한을 확인하려면 [받는 사람 사용 권한](https://go.microsoft.com/fwlink/p/?LinkId=534105)의 표에 나오는 "마이그레이션" 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>
  
<span data-ttu-id="ca85a-p105">Exchange Online PowerShell cmdlet을 사용하려면 로그인한 후 cmdlet을 로컬 Windows PowerShell 세션으로 가져와야 합니다. 해당 지침은 [원격 PowerShell을 사용하여 Exchange Online에 연결](https://go.microsoft.com/fwlink/p/?LinkId=534121)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p105">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
  
<span data-ttu-id="ca85a-117">전체 마이그레이션 명령 목록을 보려면 [이동 및 마이그레이션 cmdlet](https://go.microsoft.com/fwlink/p/?LinkId=534750)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca85a-117">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="ca85a-118">IMAP 마이그레이션에 적용되는 제한 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-118">The following restrictions apply to IMAP migrations:</span></span>
  
- <span data-ttu-id="ca85a-p106">사용자의 받은 편지함 또는 다른 메일 폴더에 있는 항목만 마이그레이션할 수 있습니다. 연락처, 일정 항목 또는 작업은 마이그레이션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p106">Only items in a user's inbox or other mail folders can be migrated. You can't migrate contacts, calendar items, or tasks.</span></span>
    
- <span data-ttu-id="ca85a-121">최대 500,000개 항목을 사용자 사서함에서 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-121">A maximum of 500,000 items can be migrated from a user's mailbox.</span></span>
    
- <span data-ttu-id="ca85a-122">마이그레이션할 수 있는 최대 메시지 크기는 35MB입니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-122">The maximum message size that can be migrated is 35 MB.</span></span>
    
## <a name="migration-steps"></a><span data-ttu-id="ca85a-123">마이그레이션 단계</span><span class="sxs-lookup"><span data-stu-id="ca85a-123">Migration steps</span></span>

### <a name="step-1-prepare-for-an-imap-migration"></a><span data-ttu-id="ca85a-124">1단계: IMAP 마이그레이션 준비</span><span class="sxs-lookup"><span data-stu-id="ca85a-124">Step 1: Prepare for an IMAP migration</span></span>
<span data-ttu-id="ca85a-125"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="ca85a-125"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="ca85a-126">**IMAP 조직에 대한 도메인이 있는 경우 Microsoft 365 조직의 허용 도메인으로 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="ca85a-126">**If you have a domain for you IMAP organization, add it as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="ca85a-127">Microsoft 365 사서함에 대해 이미 소유하고 있는 동일한 도메인을 사용하려면 먼저 이를 Microsoft 365에 허용 도메인으로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-127">If you want to use the same domain you already own for your Microsoft 365 mailboxes, you first have to add it as an accepted domain to Microsoft 365.</span></span> <span data-ttu-id="ca85a-128">추가한 후 Microsoft 365에서 사용자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-128">After you have added it, you can create your users in Microsoft 365.</span></span> <span data-ttu-id="ca85a-129">자세한 내용은[도메인 확인을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=534110)</span><span class="sxs-lookup"><span data-stu-id="ca85a-129">For more information, see[Verify your domain](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span></span>
    
- <span data-ttu-id="ca85a-130">**사서함이 있도록 각 사용자를 Microsoft 365에 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="ca85a-130">**Add each user to Microsoft 365 so that they have a mailbox.**</span></span> <span data-ttu-id="ca85a-131">자세한 내용은 비즈니스용[Microsoft 365에 사용자 추가를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=535065)</span><span class="sxs-lookup"><span data-stu-id="ca85a-131">For instructions, see[Add users to Microsoft 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=535065).</span></span>
    
- <span data-ttu-id="ca85a-p109">**IMAP 서버의 FQDN을 받습니다**. IMAP 마이그레이션 끝점을 만들 때 사서함 데이터를 마이그레이션할 원본 IMAP 서버의 FQDN(정규화된 도메인 이름)(전체 컴퓨터 이름이라고도 함)을 제공해야 합니다. IMAP 클라이언트나 PING 명령을 사용하여 인터넷에서 해당 FQDN으로 IMAP 서버와 통신할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p109">**Obtain the FQDN of the IMAP server**. You need to provide the fully qualified domain name (FQDN) (also called the full computer name) of the IMAP server that you will migrate mailbox data from when you create an IMAP migration endpoint. Use an IMAP client or the PING command to verify that you can use the FQDN to communicate with the IMAP server over the Internet.</span></span>
    
- <span data-ttu-id="ca85a-p110">**IMAP 연결을 허용하도록 방화벽을 구성** 합니다. 마이그레이션 도중에 Microsoft 데이터 센터에서 시작된 네트워크 트래픽이 IMAP 서버를 호스트하는 조직에 유입될 수 있도록 하기 위해 IMAP 서버를 호스트하는 조직의 방화벽에서 포트를 열어야 할 수도 있습니다. Microsoft 데이터 센터에서 사용하는 IP 주소 목록은 [Exchange Online URL 및 IP 주소 범위](https://go.microsoft.com/fwlink/p/?LinkId=535066)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p110">**Configure the firewall to allow IMAP connections**. You might have to open ports in the firewall of the organization that hosts the IMAP server so network traffic originating from the Microsoft datacenter during the migration is allowed to enter the organization that hosts the IMAP server. For a list of IP addresses used by Microsoft datacenters, see [Exchange Online URLs and IP Address Ranges](https://go.microsoft.com/fwlink/p/?LinkId=535066).</span></span>
    
- <span data-ttu-id="ca85a-p111">**관리자 계정에 IMAP 조직 내의 사서함에 액세스하기 위한 권한을 할당** 합니다. CSV 파일의 관리자 자격 증명을 사용하는 경우 사용하는 계정에 온-프레미스 사서함에 액세스하는 데 필요한 권한이 있어야 합니다. 사용자 사서함에 액세스하는 데 필요한 권한은 특정 IMAP 서버에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p111">**Assign the administrator account permissions to access mailboxes in your IMAP organization**. If you use administrator credentials in the CSV file, the account that you use must have the necessary permissions to access the on-premises mailboxes. The permissions required to access user mailboxes is determined by the particular IMAP server.</span></span> 
    
- <span data-ttu-id="ca85a-p112">**Exchange Online PowerShell cmdlet** 을 사용하려면 로그인한 후 cmdlet을 로컬 Windows PowerShell 세션으로 가져와야 합니다. 해당 지침은 [원격 PowerShell을 사용하여 Exchange Online에 연결](https://go.microsoft.com/fwlink/p/?LinkId=534121)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p112">**To use the Exchange Online PowerShell cmdlets**, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
    
    <span data-ttu-id="ca85a-143">전체 마이그레이션 명령 목록을 보려면 [이동 및 마이그레이션 cmdlet](https://go.microsoft.com/fwlink/p/?LinkId=534750)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca85a-143">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
    
- <span data-ttu-id="ca85a-p113">**IMAP 서버에 연결할 수 있는지 확인** 합니다. Exchange Online PowerShell에서 다음 명령을 실행하여 IMAP 서버에 대한 연결 설정을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p113">**Verify that you can connect to your IMAP server**. Run the following command in Exchange Online PowerShell to test the connection settings to your IMAP server.</span></span>
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    <span data-ttu-id="ca85a-146">**Port** 매개 변수의 값으로는 일반적으로 암호화되지 않은 연결 또는 TLS(전송 계층 보안) 연결의 경우 143을 사용하고 SSL 연결의 경우 993을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-146">For the value of the **Port** parameter, it's typical to use 143 for unencrypted or Transport Layer Security (TLS) connections and to use 993 for SSL connections.</span></span>
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a><span data-ttu-id="ca85a-147">2단계: IMAP 마이그레이션 일괄 처리를 위한 CSV 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="ca85a-147">Step 2: Create a CSV file for an IMAP migration batch</span></span>
<span data-ttu-id="ca85a-148"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="ca85a-148"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="ca85a-p114">IMAP 마이그레이션 일괄 처리에서 해당 사서함을 마이그레이션할 사용자 그룹을 식별합니다. CSV 파일의 각 행에는 IMAP 메시징 시스템의 사서함에 연결하는 데 필요한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p114">Identify the group of users whose mailboxes you want to migrate in an IMAP migration batch. Each row in the CSV file contains information necessary to connect to a mailbox in the IMAP messaging system.</span></span>
  
<span data-ttu-id="ca85a-151">각 사용자의 필수 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-151">Here are the required attributes for each user:</span></span> 
  
- <span data-ttu-id="ca85a-152">**EmailAddress는** 사용자의 Microsoft 365 사서함에 대한 사용자 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-152">**EmailAddress** specifies the user ID for the user's Microsoft 365 mailbox.</span></span>
    
- <span data-ttu-id="ca85a-153">**UserName** 은 IMAP 서버의 사서함에 액세스하는 데 사용할 계정의 로그온 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-153">**UserName** specifies the logon name for the account to use to access the mailbox on the IMAP server.</span></span>
    
- <span data-ttu-id="ca85a-154">**Password** 는 **UserName** 열에 있는 계정의 암호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-154">**Password** specifies the password for the account in the **UserName** column.</span></span>
    
<span data-ttu-id="ca85a-p115">다음은 CSV 파일 형식의 예입니다. 이 예에서는 다음 세 개의 사서함을 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p115">Here's an example of the format for the CSV file. In this example, three mailboxes are migrated:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

<span data-ttu-id="ca85a-157">**UserName** 특성의 경우, 사용자 이름 외에 IMAP 서버의 사서함에 액세스하는 데 필요한 권한이 할당된 계정의 자격 증명을 사용할 수 있습니다. 다음은 일부 IMAP 서버에 사용되는 특정 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-157">For the **UserName** attribute, in addition to the user name, you can use the credentials of an account that has been assigned the necessary permissions to access mailboxes on the IMAP server, the following are some of the specific formats used for some of the IMAP servers:</span></span>
  
 <span data-ttu-id="ca85a-158">**Microsoft Exchange**</span><span class="sxs-lookup"><span data-stu-id="ca85a-158">**Microsoft Exchange:**</span></span>
  
<span data-ttu-id="ca85a-159">Microsoft Exchange의 IMAP 구현에서 전자 메일을 마이그레이션하는 경우에는 CSV 파일에서 **UserName** 특성에 **Domain/Admin_UserName/User_UserName** 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-159">If you're migrating email from the IMAP implementation for Microsoft Exchange, use the format **Domain/Admin_UserName/User_UserName** for the **UserName** attribute in the CSV file.</span></span> <span data-ttu-id="ca85a-160">Terry Adams, Ann Beebe, Paul Cannon의 전자 메일을 Exchange에서 마이그레이션한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-160">Let's say you're migrating email from Exchange for Terry Adams, Ann Beebe, and Paul Cannon.</span></span> <span data-ttu-id="ca85a-161">사용자 이름이 **mailadmin이고** 암호가 **P \@ ssw0rd인** 메일 관리자 계정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-161">You have a mail administrator account, where the user name is **mailadmin** and the password is **P\@ssw0rd**.</span></span> <span data-ttu-id="ca85a-162">CSV 파일은 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-162">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 <span data-ttu-id="ca85a-163">**Dovecot:**</span><span class="sxs-lookup"><span data-stu-id="ca85a-163">**Dovecot:**</span></span>
  
<span data-ttu-id="ca85a-164">Dovecot IMAP 서버와 같은 SASL(Simple Authentication and Security Layer)을 지원하는 IMAP 서버의 경우 **User_UserName\*Admin_UserName** 형식을 사용하며, 여기서 추가(\*)는 구성 가능한 구분자 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-164">For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName\*Admin_UserName**, where the asterisk ( \* ) is a configurable separator character.</span></span> <span data-ttu-id="ca85a-165">관리자 자격 증명 **mailadmin** 및 **P \@ ssw0rd를** 사용하여 Dovecot IMAP 서버에서 동일한 사용자의 전자 메일을 마이그레이션하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-165">Let's say you're migrating those same users' email from a Dovecot IMAP server using the administrator credentials **mailadmin** and **P\@ssw0rd**.</span></span> <span data-ttu-id="ca85a-166">이때 CSV 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-166">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 <span data-ttu-id="ca85a-167">**Mirapoint:**</span><span class="sxs-lookup"><span data-stu-id="ca85a-167">**Mirapoint:**</span></span>
  
<span data-ttu-id="ca85a-168">Mirapoint Message Server에서 전자 메일을 마이그레이션하는 경우 관리자 자격 **증명에 \@ #user#Admin_UserName#** 형식을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ca85a-168">If you're migrating email from Mirapoint Message Server, use the format **#user\@domain#Admin_UserName#** for the administrator credentials.</span></span> <span data-ttu-id="ca85a-169">관리자 자격 증명 **mailadmin** 및 **P \@ ssw0rd를** 사용하여 Mirapoint에서 전자 메일을 마이그레이션하려면 CSV 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-169">To migrate email from Mirapoint using the administrator credentials **mailadmin** and **P\@ssw0rd**, your CSV file would look like this:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 <span data-ttu-id="ca85a-170">**Courier IMAP:**</span><span class="sxs-lookup"><span data-stu-id="ca85a-170">**Courier IMAP:**</span></span>
  
<span data-ttu-id="ca85a-171">Courier IMAP과 같은 일부 원본 전자 메일 시스템은 사서함 관리자 자격 증명을 사용하여 사서함을 Microsoft 365로 마이그레이션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-171">Some source email systems, such as Courier IMAP, don't support using mailbox admin credentials to migrate mailboxes to Microsoft 365.</span></span> <span data-ttu-id="ca85a-172">대신, 가상 공유 폴더를 사용하도록 원본 전자 메일 시스템을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-172">Instead, you can set up your source email system to use virtual shared folders.</span></span> <span data-ttu-id="ca85a-173">가상 공유 폴더를 사용하여 사서함 관리자 자격 증명을 통해 원본 전자 메일 시스템의 사용자 사서함에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-173">By using virtual shared folders, you can use the mailbox admin credentials to access user mailboxes on the source email system.</span></span> <span data-ttu-id="ca85a-174">Courier IMAP에 대한 가상 공유 폴더를 구성하는 방법에 대한 자세한 내용은 [공유 폴더](https://go.microsoft.com/fwlink/p/?LinkId=398870)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca85a-174">For more information about how to configure virtual shared folders for Courier IMAP, see [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span></span>
  
<span data-ttu-id="ca85a-p120">원본 전자 메일 시스템에서 가상 공유 폴더를 설정한 뒤 사서함을 마이그레이션하려면 선택적 특성인 **UserRoot** 를 마이그레이션 파일에 포함해야 합니다. 이 특성은 원본 전자 메일 시스템의 가상 공유 폴더 구조에서 각 사용자의 사서함 위치를 지정합니다. 예를 들어 Terry 사서함의 경로는 /users/terry.adams입니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p120">To migrate mailboxes after you set up virtual shared folders on your source email system, you have to include the optional attribute **UserRoot** in the migration file. This attribute specifies the location of each user's mailbox in the virtual shared folder structure on the source email system. For example, the path to Terry's mailbox is /users/terry.adams.</span></span>
  
<span data-ttu-id="ca85a-178">다음은 **UserRoot** 특성을 포함하는 CSV 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-178">Here's an example of a CSV file that contains the **UserRoot** attribute:</span></span>
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a><span data-ttu-id="ca85a-179">3단계: IMAP 마이그레이션 끝점 만들기</span><span class="sxs-lookup"><span data-stu-id="ca85a-179">Step 3: Create an IMAP migration endpoint</span></span>
<span data-ttu-id="ca85a-180"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="ca85a-180"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="ca85a-181">전자 메일을 마이그레이션하려면 Microsoft 365가 원본 전자 메일 시스템에 연결하고 통신해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-181">To migrate email successfully, Microsoft 365 needs to connect to and communicate with the source email system.</span></span> <span data-ttu-id="ca85a-182">이를 위해 Microsoft 365는 마이그레이션 끝점을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-182">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="ca85a-183">또한 마이그레이션 끝점은 동시에 마이그레이션할 사서함의 수와 24시간마다 수행되는 증분 동기화 중에 동시에 동기화할 사서함 수도 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-183">The migration endpoint also defines the number of mailboxes to migrate simultaneously and the number of mailboxes to synchronize simultaneously during incremental synchronization, which occurs once every 24 hours.</span></span> <span data-ttu-id="ca85a-184">IMAP 마이그레이션용 마이그레이션 끝점을 만들려면 먼저 [Exchange Online에 연결](https://go.microsoft.com/fwlink/p/?LinkId=534121)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-184">To create a migration end point for IMAP migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span> 
  
<span data-ttu-id="ca85a-185">전체 마이그레이션 명령 목록을 보려면 [이동 및 마이그레이션 cmdlet](https://go.microsoft.com/fwlink/p/?LinkId=534750)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca85a-185">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="ca85a-186">Exchange Online PowerShell에서 "IMAPEndpoint"라는 IMAP 마이그레이션 끝점을 만들려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-186">To create the IMAP migration endpoint called "IMAPEndpoint" in Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

<span data-ttu-id="ca85a-p122">동시 마이그레이션, 동시 증분 마이그레이션 및 사용할 포트를 지정하기 위한 매개 변수를 추가할 수도 있습니다. 다음 Exchange Online PowerShell 명령은 50개의 동시 마이그레이션과 최대 25개의 동시 증분 동기화를 지원하는 "IMAPEndpoint"라는 IMAP 마이그레이션 끝점을 만듭니다. 또한 TLS 암호화를 위해 포트 143을 사용하도록 끝점을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p122">You can also add parameters to specify concurrent migrations, concurrent incremental migrations, and the port to use. The following Exchange Online PowerShell command creates an IMAP migration endpoint called "IMAPEndpoint" that supports 50 concurrent migrations and up to 25 concurrent incremental synchronizations. It also configures the endpoint to use port 143 for TLS encryption.</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

<span data-ttu-id="ca85a-190">**New-MigrationEndpoint** cmdlet에 대한 자세한 내용은 [New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca85a-190">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="ca85a-191">작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="ca85a-191">Verify it worked</span></span>

<span data-ttu-id="ca85a-192">Exchange Online PowerShell에서 다음 명령을 실행하여 "IMAPEndpoint"에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-192">Run the following command in Exchange Online PowerShell to display information about the "IMAPEndpoint":</span></span>
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a><span data-ttu-id="ca85a-193">4단계: IMAP 마이그레이션 일괄 처리 만들기 및 시작</span><span class="sxs-lookup"><span data-stu-id="ca85a-193">Step 4: Create and start an IMAP migration batch</span></span>
<span data-ttu-id="ca85a-194"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="ca85a-194"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="ca85a-p123">[New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439) cmdlet을 사용하여 IMAP 마이그레이션용 마이그레이션 일괄 처리를 만들 수 있습니다. _AutoStart_ 매개 변수를 포함하면 마이그레이션 일괄 처리를 만들고 자동으로 시작할 수 있습니다. 아니면 [Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440) cmdlet을 사용해 마이그레이션 일괄 처리를 만든 다음 나중에 일괄 처리를 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-p123">You can use the [New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439) cmdlet to create a migration batch for an IMAP migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then start it afterwards by using the[Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440) cmdlet.</span></span>
  
<span data-ttu-id="ca85a-198">다음 Exchange Online PowerShell 명령은 "IMAPEndpoint"라는 IMAP 끝점을 사용하여 "IMAPBatch1"이라는 마이그레이션 일괄 처리를 자동으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-198">The following Exchange Online PowerShell command will automatically start the migration batch called "IMAPBatch1" using the IMAP endpoint called "IMAPEndpoint":</span></span>
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a><span data-ttu-id="ca85a-199">작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="ca85a-199">Verify it worked</span></span>

<span data-ttu-id="ca85a-200">[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) cmdlet을 실행하여 "IMAPBatch1"에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-200">Run the [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) cmdlet to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

<span data-ttu-id="ca85a-201">다음 명령을 실행하여 일괄 처리가 시작되었는지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-201">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="ca85a-202">5단계: Microsoft 365로 전자 메일 라우팅</span><span class="sxs-lookup"><span data-stu-id="ca85a-202">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="ca85a-203"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="ca85a-203"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="ca85a-204">전자 메일 시스템은 MX 레코드라는 DNS 레코드를 사용하여 전자 메일을 배달할 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="ca85a-205">전자 메일 마이그레이션 프로세스 중에는 MX 레코드가 원본 전자 메일 시스템을 가리켰습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-205">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="ca85a-206">이제 Microsoft 365로의 전자 메일 마이그레이션이 완료되었습니다. 이제 Microsoft 365에서 MX 레코드를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-206">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="ca85a-207">이렇게 하면 전자 메일이 Microsoft 365 사서함으로 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-207">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="ca85a-208">MX 레코드를 이동하여 준비가 되었을 때 이전 전자 메일 시스템을 해제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-208">By moving the MX record, you can also turn off your old email system when you're ready.</span></span> 
  
<span data-ttu-id="ca85a-209">DNS 공급자가 많이 있으므로 MX 레코드를 변경하기 위한 특정 지침이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-209">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="ca85a-210">사용자의 DNS 공급자가 여기에 포함되지 않거나 일반적인 지침을 원하는 경우를 위해 [일반 MX 레코드 지침](https://go.microsoft.com/fwlink/?LinkId=397449)도 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-210">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions ](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>
  
<span data-ttu-id="ca85a-p126">고객 및 파트너의 전자 메일 시스템에서 변경된 MX 레코드를 인식하는 데는 최대 72시간이 걸릴 수 있습니다. 다음 작업을 계속 진행하기 전에 적어도 72시간 동안 기다립니다. 6단계: IMAP 마이그레이션 일괄 처리 삭제</span><span class="sxs-lookup"><span data-stu-id="ca85a-p126">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: Step 6: Delete IMAP migration batch.</span></span> 
  
### <a name="step-6-delete-imap-migration-batch"></a><span data-ttu-id="ca85a-213">6단계: IMAP 마이그레이션 일괄 처리 삭제</span><span class="sxs-lookup"><span data-stu-id="ca85a-213">Step 6: Delete IMAP migration batch</span></span>
<span data-ttu-id="ca85a-214"><a name="BK_Step6"> </a></span><span class="sxs-lookup"><span data-stu-id="ca85a-214"><a name="BK_Step6"> </a></span></span>

<span data-ttu-id="ca85a-215">MX 레코드를 변경하고 모든 전자 메일이 Microsoft 365 사서함으로 라우팅되고 있는지 확인한 후 해당 메일이 Microsoft 365로 이동될 것임 사용자에게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-215">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="ca85a-216">그런 후에는 IMAP 마이그레이션 일괄 처리를 삭제해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-216">After this, you can delete the IMAP migration batch.</span></span> <span data-ttu-id="ca85a-217">마이그레이션 일괄 처리를 삭제하기 전에 다음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-217">Verify the following before you delete the migration batch.</span></span>
  
- <span data-ttu-id="ca85a-218">모든 사용자가 Microsoft 365 사서함을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-218">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="ca85a-219">일괄 처리가 삭제되고 나면 해당 Microsoft 365 사서함에 Exchange Server 사서함으로 전송되는 메일이 복사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-219">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>
    
- <span data-ttu-id="ca85a-220">Microsoft 365 사서함은 메일이 해당 사서함으로 직접 전송되는 것을 시작한 후 한 번 이상 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-220">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="ca85a-221">이 작업을 수행하기 위해 마이그레이션 일괄 처리에 대한 마지막 동기화 시간 상자의 값이 메일이 Microsoft 365 사서함으로 직접 라우팅하기 시작한 시간보다 최신 상태인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-221">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>
    
<span data-ttu-id="ca85a-222">Exchange Online PowerShell에서 "IMAPBatch1" 마이그레이션 일괄 처리를 삭제하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-222">To delete the "IMAPBatch1" migration batch from Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

<span data-ttu-id="ca85a-223">**Remove-MigrationBatch** cmdlet에 대한 자세한 내용은 [Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca85a-223">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="ca85a-224">작동하는지 확인</span><span class="sxs-lookup"><span data-stu-id="ca85a-224">Verify it worked</span></span>

<span data-ttu-id="ca85a-225">Exchange Online PowerShell에서 다음 명령을 실행하여 "IMAPBatch1"에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-225">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

<span data-ttu-id="ca85a-226">이 명령을 실행하면 상태가 **제거 중** 인 마이그레이션 일괄 처리가 반환되거나, 마이그레이션 일괄 처리를 찾을 수 없다는 오류가 반환됩니다. 이 경우 해당 일괄 처리가 삭제되었음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca85a-226">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="ca85a-227">**Get-MigrationBatch** cmdlet에 대한 자세한 내용은 [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca85a-227">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ca85a-228">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca85a-228">See also</span></span>

[<span data-ttu-id="ca85a-229">IMAP 마이그레이션 문제 해결사</span><span class="sxs-lookup"><span data-stu-id="ca85a-229">IMAP Migration Troubleshooter</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536482)

