---
title: Microsoft 365의 Microsoft Information Protection
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: MIP(Microsoft Information Protection)를 구현하여 중요한 정보를 어디에서나 보호할 수 있습니다.
ms.openlocfilehash: 5b9484826f0d3a297dae47c7d140d93297473023
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259301"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365의 Microsoft Information Protection

>*[Microsoft 365 보안 및 규정 준수 라이선스](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

MIP(Microsoft Information Protection)를 구현하면 중요한 정보를 언제 어디서나 검색, 분류 및 보호할 수 있습니다.

MIP 기능은 Microsoft 365 규정 준수에 포함되어 있으며, [데이터 파악](#know-your-data), [데이터 보호](#protect-your-data) 및 [데이터 손실 방지](#prevent-data-loss)를 위한 도구를 제공합니다.

![MIP를 통해 중요한 데이터를 검색, 분류 및 보호하는 방법에 대한 이미지](../media/powered-by-intelligent-platform.png)

:::image type="content" source="../media/data-table1-4638524-new.png" alt-text="사용자 데이터 파악":::

데이터 관리에 대한 자세한 내용은 [Microsoft 365에서 Microsoft 정보 관리](manage-Information-governance.md)를 참조합니다.

## <a name="know-your-data"></a>사용자 데이터 파악

> [!NOTE]
> 현재 미리 보기에 있는 Azure Purview에서 데이터 분류 및 레이블 지정에 대한 자세한 내용은 [Azure Purview에서 내용에 자동으로 레이블을 지정](/azure/purview/create-sensitivity-label)을 참조하세요.
> 
> Azure Purview의 릴리스 공지 사항은 다음 블로그 게시물을 참조하세요. [Microsoft Information Protection 및 Microsoft Azure Purview: 함께 사용하면 더욱 효과적](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481) 및 [Spring Ignite 2021의 Azure Purview](https://techcommunity.microsoft.com/t5/azure-purview/azure-purview-at-spring-ignite-2021/ba-p/2175919).

하이브리드 환경에서 데이터 환경을 이해하고 중요한 데이터를 식별하려면 다음 기능을 사용합니다.

:::image type="content" source="../media/knowyourdata-new.png" alt-text="사용자 데이터 파악"::: 


|**기능**|**어떤 문제를 해결하나요?**|**시작**|**라이선스**|
|--|--|--|--|
|[중요한 정보 유형](sensitive-information-type-entity-definitions.md)| 키워드, 신뢰 수준 및 근접성을 포함하는 확증적 증거와 함께 기본 제공 또는 사용자 정의 정규식 또는 함수를 사용하여 중요한 데이터를 식별합니다. 중요한 정보 유형을 사용하여 조직에서 특정 유형의 데이터를 식별합니다. 즉시 이용 가능한 중요한 정보 유형을 사용하여 표준 데이터 형식(예: 여권 번호)을 찾을 수 있습니다. 사용자 지정 정보 유형을 만들어 부품 번호와 같은 환경에 고유한 정보를 식별합니다. | [기본 제공 중요한 정보 유형 사용자 지정](customize-a-built-in-sensitive-information-type.md)| |
|[교육 가능한 분류자(미리 보기)](classifier-learn-about.md)| 기본 제공 분류자 중 하나를 사용하여 데이터를 분류하거나 고유한 내용을 사용하여 분류자를 교육합니다. | [학습 가능한 분류자 시작(미리 보기)](classifier-get-started-with.md)| |
|[데이터 분류](data-classification-overview.md) | 민감도 레이블, 보존 레이블이 있거나 조직에서 중요한 정보 유형으로 분류된 항목과 사용자가 수행하는 작업을 식별합니다.  | [콘텐츠 탐색기로 시작](data-classification-content-explorer.md)<br /><br /> [활동 탐색기 시작하기](data-classification-activity-explorer.md)| |



## <a name="protect-your-data"></a>사용자 데이터 보호

암호화, 액세스 제한 및 시각적 표시를 포함한 유연한 보호 작업을 적용하려면 다음 기능을 사용합니다.


:::image type="content" source="../media/protectyourdata-4638524-new.png" alt-text="사용자 데이터 보호":::

|**기능**|**어떤 문제를 해결하나요?**|**시작**|**라이선스**|
|--|--|--|--|
|[민감도 레이블](sensitivity-labels.md)| 애플리케이션, 서비스 및 장치에 걸친 단일 솔루션으로 조직 내외부에서 데이터를 이동할 때 레이블을 지정하고 보호합니다. <br /><br />시나리오 예: [Power BI 민감도 레이블을 적용하고 내보낼 때 데이터 보호](/power-bi/admin/service-security-apply-data-sensitivity-labels)|[민감도 레이블 시작](get-started-with-sensitivity-labels.md) |
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| 클라우드에 있는 데이터 저장소에 있는 중요한 정보를 검색, 레이블 지정 및 보호 | [클라우드에 저장된 데이터를 검색하고, 분류하고, 레이블을 지정하고, 보호](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[정보 보호 통합 라벨링 스캐너](/azure/information-protection/deploy-aip-scanner)| 사내에 있는 데이터 저장소에 있는 중요한 정보를 검색, 레이블 지정 및 보호합니다. | [Azure Information Protection 통합 라벨링 스캐너 구성 및 설치](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[활동 탐색기]()||||


## <a name="transition-from-aip-to-mip"></a>AIP에서 MIP로 전환
클래식 Azure Information Protection 관리자 환경 및 클라이언트는 내년 초에 사용이 중지됩니다. Microsoft Information Protection으로 이전하는 것이 좋습니다. 이 작업에는 기존 레이블 및 정책 모두에 대한 마이그레이션 작업이 수반됩니다. 

:::image type="content" source="../media/transition-aip2mip-4638524-new.png" alt-text="AIP에서 MIP로 전환":::

## <a name="additional-capabilities"></a>추가 기능
Microsoft 365에는 데이터를 보호하는 데 도움이 되는 기능이 포함되어 있습니다.

|**기능**|**어떤 문제를 해결하나요?**|**시작**|
|--|--|--|
| OME(Office 365 메시지 암호화) | 모든 장치에서 사용자에게 전송되는 전자 메일 메시지와 첨부된 문서를 암호화하여 권한이 있는 수신자만 전자 메일 정보를 읽을 수 있도록 합니다. <br /><br /> 시나리오 예: 고급 메시지 암호화로 암호화된 전자 메일 취소 | 새 메시지 암호화 기능 설정하기 |
| 이중 키 암호화 | 모든 경우 사용자만 보호된 콘텐츠를 해독할 수 있으며, 규정 요구 사항을 충족하려면 암호화 키를 지리적 경계 내에 보관해야 합니다. | 이중 키 암호화 |  
| 고객 키를 사용한 서비스 암호화 | 권한이 없는 시스템이나 직원이 데이터를 볼 수 없도록 보호하고 Microsoft 데이터 센터에서 BitLocker 디스크 암호화를 보완합니다. | Office 365의 고객 키 설정 |
| IRM(정보 권한 관리) | 사용자가 문서를 체크아웃하면 권한이 있는 사용자만 사용자가 지정한 정책에 따라 파일을 보고 사용할 수 있도록 다운로드된 파일이 보호되도록 SharePoint 목록 및 라이브러리를 보호합니다. | SharePoint 관리 센터의 IRM(정보 권한 관리) 설정 |
| 권한 관리 커넥터 | Exchange 또는 SharePoint Server 및 FCI(파일 분류 인프라)를 사용하는 기존 온-프레미스 배포에 대해서만 보호 | RMS 커넥터를 배포하는 단계 |



## <a name="prevent-data-loss"></a>데이터 손실 방지

중요한 정보의 우발적인 과다 공유를 방지하려면 다음 기능을 사용합니다.

:::image type="content" source="../media/dlp-4638524-new.png" alt-text="데이터 손실 방지":::

|**단계**|**설명**|**추가 정보**|
|--|--|--|
|[DLP 정책 디자인](data-loss-prevention-policies.md)| 정보 식별 모드 계획(중요한 정보 유형, 레이블, 기타) <br /><br /> 정책에서 대상을 지정하는 위치(서비스, 클라이언트, 타사 앱)를 계획합니다. <br /><br /> 정책 팁 계획, 기타||
||||




|**기능**|**어떤 문제를 해결하나요?**|**시작**|
|--|--|--|
|[데이터 손실 방지에 대한 자세한 정보](dlp-learn-about-dlp.md)| 중요한 항목의 의도하지 않은 공유를 방지하는 데 도움이 됩니다. | [기본 DLP 정책을 사용하여 시작](get-started-with-the-default-dlp-policy.md)|
|[끝점 데이터 손실 방지에 대한 자세한 정보](endpoint-dlp-learn-about.md)| DLP 기능을 Windows 10 컴퓨터에서 사용 및 공유되는 항목으로 확장합니다. | [끝점 데이터 손실 방지 시작](endpoint-dlp-getting-started.md)|
|[Microsoft 규정 준수 확장(미리 보기)에 대해 알아보기](dlp-chrome-learn-about.md) | Chrome 브라우저로 DLP 기능 확장 | [Microsoft 규정 준수 확장 시작(미리 보기)](dlp-chrome-get-started.md)|
|[Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 알아보기(미리 보기)](dlp-on-premises-scanner-learn.md)|파일 활동과 해당 파일에 대한 보호 작업 모니터링을 온-프레미스 파일 공유와 SharePoint 폴더 및 문서 라이브러리로 확대시킵니다.|[Microsoft 365 데이터 손실 방지 온-프레미스 스캐너로 시작하기(미리 보기)](dlp-on-premises-scanner-get-started.md)|
|[Microsoft Teams 대화 및 채널 메시지에서 중요한 정보를 보호합니다](dlp-microsoft-teams.md) | Teams 채팅 및 채널 메시지로 일부 DLP 기능 확장 | [Microsoft Teams의 기본 데이터 손실 방지 정책에 대한 자세한 정보(미리 보기)](dlp-teams-default-policy.md)| 


## <a name="additional-resources"></a>추가 리소스

여러 조직에서는 데이터 개인 정보 보호 규정을 준수하기 위해 이러한 정보 보호 기능을 사용하고 있습니다. Microsoft는 안전한 액세스, 위협 방지, 정보 보호, 데이터 거버넌스를 비롯한 Microsoft 365 전반에서 기능을 계획하고 구현하기 위한 종단 간 프로세스를 안내하는 워크플로를 설계했습니다. 자세한 내용은 [Microsoft 365를 사용하여 데이터 개인 정보 보호 규정을 위한 정보 보호를 구현합니다](../solutions/information-protection-deploy.md)(aka.ms/m365dataprivacy)를 참조하세요. 

또한 정보 보호 기능을 구현하기 위한 통합 전략을 계획할 수 있도록 *Microsoft 365 정보 보호 및 규정 준수 기능* 일러스트레이션 집합을 다운로드하세요.  사용자는 개인적으로 이 일러스트레이션을 사용할 수 있습니다.

| 항목 | 설명 |
|:-----|:------------|
|[![모델 포스터: Microsoft 365 정보 보호 및 규정 준수 기능](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> [PDF로 다운로드](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Visio로 다운로드](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> 일본어: [PDF로 다운로드](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Visio로 다운로드](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> 업데이트 날짜: 2020년 10월|포함 항목: <ul><li>  Microsoft 정보 보호 및 데이터 손실 방지</li><li>보존 정책 및 보존 레이블 </li><li>정보 장벽</li><li>커뮤니케이션 규정 준수</li><li>내부자 위험 관리</li><li>타사 데이터 수집</li>|

