```bash
$ aws cloudformation validate-template --template-body template.yml

An error occurred (ValidationError) when calling the ValidateTemplate operation: Template format error: unsupported structure.
```

--template-body にはパスに"file://"をつける。

```bash
$ aws cloudformation validate-template --template-body file://template.yml
{
    "Parameters": []
}
```

create stack

```bash
$ aws cloudformation create-stack --stack-name MyFormation --template-body file://template.yml
{
    "StackId": "arn:aws:cloudformation:ap-northeast-1:865422985541:stack/MyFormation/d294a980-5619-11e9-80b0-0e72822fc3e0"
}
```

delete stack

```bash
$ aws cloudformation delete-stack --stack-name MyFormation
```

change set

```bash
$ aws cloudformation create-change-set --stack-name MyFormation --change-set-name MyFormationChangeSet --template-body file://template.yml
```
