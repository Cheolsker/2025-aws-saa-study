
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
  - Amazon EFS는 주로 *Linux 기반 파일 시스템(NFS 프로토콜 사용)용* 으로 설계
  - Windows EC2 인스턴스는 EFS를 마운트할 수 있지만, 기본적으로 Windows 기반 애플리케이션에 필요한 *네이티브 SMB 지원 및 NTFS 권한*을 제공하지 않음

- D 
  - Amazon EBS는 블록 스토리지이며, *단일 EC2 인스턴스에 연결되도록 설계*됨.
  - 기본적으로 여러 EC2 인스턴스(특히 여러 AZ에 걸쳐)에 동시에 마운트되는 공유 파일 시스템을 지원하지 않음.


## 참고
- AWS Storage Gateway
  - Volumn, File, Tape
- Amzaon FSx
- Amazon EFS
- Amazon EBS



# 2번
정답 > 

## 근거



# 3번
정답 > 

## 근거



# 4번
정답 > 

## 근거



# 5번
정답 >

## 근거

