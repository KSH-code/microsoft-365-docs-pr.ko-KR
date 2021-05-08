---
title: Microsoft 365의 Microsoft 정보 거버넌스
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
recommendations: false
description: Microsoft 정보 거버넌스 기능을 구현하여 규정 준수 또는 규제 요구 사항에 대한 데이터를 관리합니다.
ms.openlocfilehash: 304b4e57702c55242e49fae7fdf4a36e9b2f7cdb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244567"
---
# <a name="microsoft-information-governance-in-microsoft-365"></a>Microsoft 365의 Microsoft 정보 거버넌스

>*[보안 및 규정 준수에 대한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Microsoft 정보 거버넌스(MIG) 기능을 사용하여 규정 준수 또는 규제 요구 사항에 대한 데이터를 관리합니다.

![데이터 관리 - 정보 거버넌스 및 레코드 관리](../media/information-governance-records-management.png)

데이터 보호에 대해 찾고 있으신가요? [Microsoft 365의 Microsoft 정보 보호](information-protection.md)를 참조하세요.

Microsoft는 사용자가 데이터 개인 정보 보호 규정을 준수할 수 있도록 안전한 액세스, 위협 방지, 정보 보호, 데이터 거버넌스를 비롯한 Microsoft 365 전반에서 기능을 계획하고 구현하기 위한 종단 간 프로세스를 안내하는 워크플로를 설계했습니다. 자세한 내용은 [Microsoft 365를 사용하여 데이터 개인 정보 보호 규정을 위한 정보 보호를 구현합니다](../solutions/information-protection-deploy.md)(aka.ms/m365dataprivacy)를 참조하세요. 

## <a name="information-governance"></a>정보 거버넌스

필요한 사항은 보존하고 필요하지 않은 사항을 삭제하려면 다음과 같이 수행하세요.
 
|기능|어떤 문제를 해결하나요?|시작|
|:------|:------------|:--------------------|:-----------------------------|
|[보존 정책 및 보존 레이블](retention.md)| 정책 관리와 전자 메일, 문서, 인스턴트 메시지 등의 삭제 워크플로를 사용하여 콘텐츠 보존 또는 삭제 <br /><br />시나리오 예시: [보존 레이블을 콘텐츠에 자동으로 적용](apply-retention-labels-automatically.md) | [보존 정책 및 보존 레이블 시작하기](get-started-with-retention.md)|
|[서비스 가져오기](importing-pst-files-to-office-365.md)| Exchange Online 사서함으로 PST 파일을 대량으로 가져오고 규정 준수 또는 규제 요구 사항에 대한 전자 메일 메시지를 보존하고 검색할 수 있습니다. | [네트워크 업로드를 사용하여 조직의 PST 파일을 Microsoft 365로 가져오기](use-network-upload-to-import-pst-files.md)|
|[타사 데이터 보관](archiving-third-party-data.md)| 소셜 미디어 플랫폼, 인스턴트 메시징 플랫폼 및 문서 공동 작업 플랫폼에서 타사 데이터에 준수 솔루션 가져오기, 보관 및 적용하기| [타사 커넥터](archiving-third-party-data.md#third-party-data-connectors)|
|[비활성 사서함](inactive-mailboxes-in-office-365.md)| 직원이 조직을 떠난 후 사서함 콘텐츠 보존 | [비활성 사서함 생성 및 관리](create-and-manage-inactive-mailboxes.md)|

## <a name="records-management"></a>레코드 관리

법적, 비즈니스 또는 규제 의무 사항에 대해 가치가 높은 콘텐츠를 관리하려면 다음과 같이 수행하세요.

|기능|어떤 문제를 해결하나요?|시작|
|:------|:------------|---------------------|:----------------------------|
|[레코드 관리](records-management.md)| 레코드 선언, 보존 및 처리를 사용하여 콘텐츠의 전체 수명을 지원하는 파일 계획에서 보존 일정 및 요구 사항을 통합하는 전자 메일 및 문서에 대한 단일 솔루션 <br /><br />시나리오 예시: [레코드의 처리](disposition.md#disposition-of-records)|[레코드 관리 시작](get-started-with-records-management.md) |