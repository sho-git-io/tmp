```mermaid
graph TD;
    A[ソースS3バケット<br>(ソースコード)]
    B[CodePipeline<br>Sourceステージ]
    C[CodePipeline<br>Buildステージ]
    D[BuildProject<br>(CodeBuild)]
    E[Artifact Bucket<br>(ビルド成果物)]
    F[CodePipeline<br>Manual Approval]
    G[承認済み成果物]
    H[CloudWatch Events<br>(スケジュール: 毎日午前2時)]
    I[DeployProject<br>(CodeBuild)]
    J[Destination S3バケット<br>(反映先)]

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G
    G --> H
    H --> I
    I --> J
