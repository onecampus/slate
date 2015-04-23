# 错误码

<aside class="notice">学壹传媒api错误码, 参考[rails render](http://guides.rubyonrails.org/layouts_and_rendering.html)</aside>

学壹传媒api错误码:


HTTP返回码 | 描述 | 符号
---|---|---
200 | 成功 | :ok
201 | 数据新建成功 | :created
401 | 未授权 | :unauthorized
403 | 禁止访问 | :forbidden
404 | 404 | :not_found
422 | 数据更新(包括新建，更新，删除)失败 | :unprocessable_entity
500 | 服务器内部错误 | :internal_server_error
501 | 未实现 | :not_implemented
1201| 已注册(自定义) | :already_registered
1251| 已关注(自定义) | already_followed
1401| access_token未发送(自定义) | :none_token
1402| access_token已过期(自定义) | :token_expired
1411| 用户名或密码错误(自定义) | :invide_name_or_pass
1451| 缺少followable id(自定义) | none_followable_id
1452| 不能关注自己(自定义) | cannot_follow_self
