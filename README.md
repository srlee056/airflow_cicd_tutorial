# airflow_cicd_tutorial

## 1. 구글 계정 생성
- GCP 무료 크레딧을 위한 새 계정 생성
- 기존 계정(무료 크레딧 모두 소모) 사용시 리소스 조심해서 사용 바람
## 2. GCE VM 생성 및 airflow 서버 올리기
- [블로그 글 참고](https://srlee056.github.io/p/docker-desktop/)
- 
## 3. GitHub Actions workflow 생성
### CI
- GitHub Actions에서 제공하는 [pylint workflow](https://github.com/srlee056/airflow_cicd_tutorial/new/main?filename=.github%2Fworkflows%2Fpylint.yml&workflow_template=ci%2Fpylint)
- [workflow 참고 1](https://github.com/EcoDataFlow/EcoDataFlow-airflow-repo/blob/main/.github/workflows/airflow-dags-test.yml)
- [workflow 참고 2](https://github.com/zizzic/airflow_repo/blob/main/.github/workflows/sync_dag_code.yml#L37)
### CD
#### script 사용
- google sdk 사용하는 방식
- [workflow 파일 참고](https://github.com/hunsoodev/dev-course-project-03/blob/main/.github/workflows/sync-gcp-instance.yml)
#### docker image 사용
- docker compose 파일에 service로 추가하는 방식
- [docker compose 파일 참고](https://github.com/EcoDataFlow/EcoDataFlow-airflow-repo/blob/main/docker-compose.server.yaml#L283)
#### self-hosted runner 사용
- self-hosted runner를 사용하면, VM 환경에 해당 repository의 코드가 한번 다운로드 되는 것을 활용한 방식
- [workflow 파일 참고](https://github.com/zizzic/airflow_repo/blob/main/.github/workflows/sync_dag_code.yml#L73)
