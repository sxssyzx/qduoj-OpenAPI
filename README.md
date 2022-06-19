# OnlineJudgeOpenAPI文档

为了方便与Virtual Judge和第三方论坛等进行集成，开放了获取题目详细信息、提交代码、获取代码运行结果和用户SSO单点登录四个API。

文档 http://qingdaou.github.io/OnlineJudgeOpenAPI/

# Notes

Response Code of a submission(Judger):

```json
{
    "accepted": 0,
    "runtime_error": 1,
    "time_limit_exceeded": 2,
    "memory_limit_exceeded": 3,
    "compile_error": 4,
    "format_error": 5,
    "wrong_answer": 6,
    "system_error": 7,
    "waiting": 8
}
```
