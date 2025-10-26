
# 1번
## 요구사항
- AWS로 마이그레이션해야 하는 Windows 기반 애플리케이션이 여러 가용성 영역(AZ)에 배포된 여러 Amazon EC2 Windows 인스턴스에 연결된 공유 Windows 파일 시스템을 사용해야 한다

## 정답
- B

EFS -> 여러 AZ의 파일시스템을 확장/축소할 수 있지않음?
EBS -> EBS는 EC2 인스턴스마다 연결하는 거 아님?
  스냅샷을 찍어야 다른 AZ에 복제할 수 있음. S3에 저장.

## 근거
- A ❌
  - "볼륨 게이트웨이 모드(Volume Gateway mode)"는 AWS Storage Gateway 서비스의 세 가지 주요 유형(Volume, File, Tape) 중 하나로, 주로 온프레미스(On-premises) 환경의 애플리케이션에 iSCSI(Internet Small Computer System Interface) 블록 스토리지를 제공하면서, 그 데이터를 클라우드(Amazon S3)에 백업 또는 저장할 수 있도록 하는 하이브리드 클라우드 스토리지 솔루션

- B ✅
  - Amazon FSx for Windows File Server는 AWS 클라우드에서 완전히 관리되는 확장 가능하고 안정적이며 안전한 네이티브 Microsoft Windows 파일 시스템을 제공
  - Windows Server의 모든 기능(예: SMB 프로토콜 지원, NTFS, Active Directory 통합)을 지원
  - 표준 SMB 프로토콜을 사용하여 여러 AZ에 걸쳐 배포된 Windows EC2 인스턴스가 공유 파일 시스템에 동시에 액세스할 수 있음

- C ❌
  - Amazon EFS는 주로 `Linux 기반 파일 시스템(NFS 프로토콜 사용)용` 으로 설계
  - Windows EC2 인스턴스는 EFS를 마운트할 수 있지만, 기본적으로 Windows 기반 애플리케이션에 필요한 `네이티브 SMB 지원 및 NTFS 권한`을 제공하지 않음

- D 
  - Amazon EBS는 블록 스토리지이며, `단일 EC2 인스턴스에 연결되도록 설계`됨.
  - 기본적으로 여러 EC2 인스턴스(특히 여러 AZ에 걸쳐)에 동시에 마운트되는 공유 파일 시스템을 지원하지 않음.



# 2번

## 정답
- C

## 근거
- A ❌
  - `Amazon Inspector`
    - EC2 인스턴스 또는 컨테이너 이미지의 보안 취약점을 평가하고 감지하는 서비스
    - 실시간 DDoS 공격을 감지하거나 완화하는 도구가 아님.
    - ALB에는 Inspector 에이전트를 설치할 수도 없음.

- B ❌
  - `Amazon Macie`
    - Amazon S3에 저장된 데이터에서 **민감한 정보(예: 개인 식별 정보)**를 식별하고 보호하는 데 중점을 둔 데이터 보안 및 개인 정보 보호 서비스

- C ✅
 - `AWS Shield Standard`
  - 모든 AWS 고객에게 자동으로 제공되어 가장 일반적인 `네트워크 및 전송 계층 DDoS 공격`으로부터 보호
 - `AWS Shield Advanced`
  - 표준 보호 이상의 기능이 필요할 때 사용
  - Shield Advanced 는 추가 비용을 내고 추가적인 서비스를 제공받는 것으로 L7 트래픽 모니터링, 사후 분석 등의 기능을 제공함
  - EC2, ELB, Cloudfront, Global Accelerator, Route 53 와 연동된 애플리케이션에 대한 추가적인 보호 가능
  - **AWS의 전담 DDoS 대응팀(DRT)**의 지원을 받음 - 연중무휴(24/7) 전문 엔지니어의 상시 지원

- D ❌
  - `Amazon GuardDuty`
    - `AWS 계정과 워크로드를 보호하는 지능형 위협 탐지 서비스`
    - 비정상적인 API 호출, 무단 액세스 등 잠재적인 보안 위협을 모니터링하고 경고 
    - 계정/인프라 보안 침해(행동의 질적 위협)를 탐지하는 데 중점
      - 예시)
      - 해외 IP에서 수많은 인스턴스를 시작하려는 시도
      - EC2 인스턴스가 암호화폐 채굴에 사용되거나, 승인되지 않은 포트에서 통신하는 등 비정상적인 동작을 보이는 경우
      - EC2 인스턴스에 대한 무차별 대입 공격(Brute-force attack) 시도.
      - S3 버킷에 대한 비정상적이거나 의심스러운 접근 패턴.



# 3번
정답 > 

## 근거



# 4번
정답 > 

## 근거



# 5번
정답 >

## 근거

