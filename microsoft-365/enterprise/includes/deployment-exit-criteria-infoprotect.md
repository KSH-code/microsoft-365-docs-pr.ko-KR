<a name="crit-infoprotect-step1"></a>
### <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>필수: 조직의 보안 및 정보 보호 수준 정의

조직에 필요한 보안 수준을 계획하고 결정해야 합니다. 이러한 수준은 최소 보안 수준과 함께 점점 중요해지는 정보 및 이에 필요한 데이터 보안에 대한 추가 수준을 정의합니다.

최소한 다음과 같은 세 가지 수준의 정보 보호를 사용하고 있습니다.

- 기준
- 중요
- 높은 규제

필요한 경우 [1단계](../infoprotect-define-sec-infoprotect-levels.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step4"></a>
### <a name="required-increased-security-for-office-365-is-configured"></a>필수: Office 365에 대한 향상된 보안 구성

[향상된 보안을 위한 Office 365 테넌트 구성](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)의 정보를 바탕으로 향상된 보안을 위해 다음 설정을 구성해야 합니다.

- Office 365 보안 및 준수 센터의 위협 관리 정책
- 추가 Exchange Online 테넌트 수준 설정
- SharePoint 관리 센터의 테넌트 수준 공유 정책
- Azure Active Directory의 설정

또한 [Office 365 ATP(Advanced Threat Protection)를 사용하도록 설정](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)해야 합니다.

필요한 경우 [3단계](../infoprotect-configure-increased-security-office-365.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step3"></a>
### <a name="optional-classification-is-configured-across-your-environment"></a>선택: 전체 사용자 환경에서 분류 구성

법률 및 준수 팀과 함께 조직의 데이터에 대한 적절한 분류 및 레이블 지정 체계를 개발하기 위해 작업하였으며, 그 내용은 다음과 같습니다.

- 중요한 데이터 유형
- Office 365 레이블
- Azure Information Protection 레이블

필요한 경우 [2단계](../infoprotect-configure-classification.md)를 통해 이 요구 사항을 충족할 수 있습니다. 

<a name="crit-infoprotect-step5"></a>
### <a name="optional-configure-privileged-access-management-in-office-365"></a>선택 사항: Office 365의 권한이 부여된 액세스 관리 구성

[Office 365의 권한이 부여된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 항목의 정보를 사용하여 권한이 부여된 액세스를 사용하도록 설정하고 Office 365 조직에서 하나 이상의 권한이 부여된 액세스 정책을 만듭니다. 이러한 정책을 구성했으며 중요한 데이터 액세스 또는 중요한 구성 설정 액세스를 위해 JIT(Just-In-Time) 액세스가 사용되도록 설정되었습니다.

필요한 경우 [4단계](../infoprotect-configure-privileged-access-management.md)를 통해 이 요구 사항을 충족할 수 있습니다. 
