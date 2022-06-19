# QDU OJ OpenAPI文档

为了方便与Virtual Judge和第三方论坛等进行集成，开放了获取题目详细信息、提交代码、获取代码运行结果和用户SSO单点登录四个API。

文档 http://qingdaou.github.io/OnlineJudgeOpenAPI/

# Notes

Response Code of a submission(Judger) is absolutely wrong!

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

Acutally, in `Judger/src/runner.h`

```cpp
enum {
    WRONG_ANSWER = -1,
    CPU_TIME_LIMIT_EXCEEDED = 1,
    REAL_TIME_LIMIT_EXCEEDED = 2,
    MEMORY_LIMIT_EXCEEDED = 3,
    RUNTIME_ERROR = 4,
    SYSTEM_ERROR = 5
};

```

in `Judger/Bindings/Python/_judger/__init__.py`

```python
RESULT_SUCCESS = 0
RESULT_WRONG_ANSWER = -1
RESULT_CPU_TIME_LIMIT_EXCEEDED = 1
RESULT_REAL_TIME_LIMIT_EXCEEDED = 2
RESULT_MEMORY_LIMIT_EXCEEDED = 3
RESULT_RUNTIME_ERROR = 4
RESULT_SYSTEM_ERROR = 5

ERROR_INVALID_CONFIG = -1
ERROR_FORK_FAILED = -2
ERROR_PTHREAD_FAILED = -3
ERROR_WAIT_FAILED = -4
ERROR_ROOT_REQUIRED = -5
ERROR_LOAD_SECCOMP_FAILED = -6
ERROR_SETRLIMIT_FAILED = -7
ERROR_DUP2_FAILED = -8
ERROR_SETUID_FAILED = -9
ERROR_EXECVE_FAILED = -10
ERROR_SPJ_ERROR = -11
```
