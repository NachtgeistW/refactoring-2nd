模块和函数是软件的骨肉，而 API 则是将骨肉连接起来的关节。易于理解和使用的 API 非常重要，但同时也很难获得。随着对软件理解的加深，我会学到如何改进 API，这时我便需要对 API 进行重构。

好的 API 会把更新数据的函数与只是读取数据的函数清晰分开。如果我看到这两类操作被混在一起，就会用[[第 11 章 重构 API/11.1 Separate Query from Modifier|将查询函数和修改函数分离]]（306）将它们分开。如果两个函数的功能非常相似、只有一些数值不同，我可以用[[第 11 章 重构 API/11.2 Parameterize Function|函数参数化]]（310）将其统一。但有些参数其实只是一个标记，根据这个标记的不同，函数会有截然不同的行为，此时最好用[[移除标级参数|移除标记参数]]（314）将不同的行为彻底分开。

在函数间传递时，数据结构常会毫无必要地被拆开，我更愿意用[[第 11 章 重构 API/11.4 Preserve Whole Object|保持对象完整]]（319）将其聚拢。函数需要的一份信息，究竟何时应该作为参数传入、何时应该调用一个函数获得，这是一个需要反复推敲的决定，推敲的过程中常常要用到[[第 11 章 重构 API/11.5 Replace Parameter with Query|以查询取代参数]]（324）和以参数取代查询（327）。

类是一种常见的模块形式。我希望尽可能保持对象不可变，所以只要有可能，我就会使用[[第 11 章 重构 API/11.7 Remove Setting Method|移除设值函数]]（331）。当调用者要求一个新对象时，我经常需要比构造函数更多的灵活性，可以借助[[../第 11 章 重构 API/11.8 Replace Constructor with Factory Function|以工厂函数取代构造函数]]（334）获得这种灵活性。

有时你会遇到一个特别复杂的函数，围绕着它传入传出一大堆数据。最后两个重构手法专门用于破解这个难题。我可以用[[第 11 章 重构 API/11.9 Replace Function with Command|以命令取代函数]]（337）将这个函数变成对象，这样对函数体使用[[第 6 章 第一组重构/6.1 Extract Function|提炼函数]]（106）时会更容易。如果稍后我对该函数做了简化，不再需要将其作为命令对象了，可以用[[第 11 章 重构 API/11.10 Replace Command with Function|以函数取代命令]]（344）再把它变回函数。

[[第 11 章 重构 API/11.1 Separate Query from Modifier]]

[[第 11 章 重构 API/11.2 Parameterize Function]]

[[第 11 章 重构 API/11.3 Remove Flag Argument]]

[[第 11 章 重构 API/11.4 Preserve Whole Object]]

[[第 11 章 重构 API/11.5 Replace Parameter with Query]]

[[第 11 章 重构 API/11.6 Replace Query with Parameter]]

[[第 11 章 重构 API/11.7 Remove Setting Method]]

[[第 11 章 重构 API/11.8 Replace Constructor with Factory Function]]

[[第 11 章 重构 API/11.9 Replace Function with Command]]

[[第 11 章 重构 API/11.10 Replace Command with Function]]
