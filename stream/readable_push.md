
不推荐使用 `readable.push('')`。

向一个非对象模式的流推入一个零字节的字符串、`Buffer` 或 `Uint8Array` 会产生副作用。
因为调用了 [`readable.push()`][stream-push]，该调用会结束读取进程。
然而，因为参数是一个空字符串，没有数据被添加到可读缓冲, 所以也就没有数据可供用户消费。

