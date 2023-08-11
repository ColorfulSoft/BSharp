<p align="center">
  <img width="100" height="100" src="https://github.com/ColorfulSoft/BSharp/blob/main/.content/B%23.png">
</p>

#

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

[![.NET](https://img.shields.io/badge/--512BD4?logo=.net&logoColor=ffffff)](https://dotnet.microsoft.com/)

![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![macOS](https://img.shields.io/badge/mac%20os-000000?style=for-the-badge&logo=macos&logoColor=F0F0F0)
![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)

# About

B# is a dynamically typed multi-paradigm programming language designed for writing high-level modules (like machine learning pipeline using ML.NET) in .NET applications.

<table>
<tr>
<td> C# 11 </td>
<td> B# </td>
</tr>
<tr>
<td>

```C#
using System;
using torch = System.AI.torch;
using nn = System.AI.torch.nn;
using F = System.AI.torch.nn.functional;
using optim = System.AI.torch.optim;

public sealed class LinearRegression : nn.Module
{

  public nn.Parameter weight;

  public nn.Parameter bias;

  public LinearRegression()
  {
    this.weight = new nn.Parameter(torch.randn());
    this.bias = new nn.Parameter(torch.randn());
  }

  public torch.Tensor forward(torch.Tensor x)
  {
    return x * this.weight + this.bias;
  }

}

static (torch.Tensor, torch.Tensor) GetData(int batch_size)
{
  return (torch.randn(batch_size), torch.randn(batch_size));
}

static void Main()
{
  var regr = new LinearRegression();
  var opt = new optim.SGD(regr.parameters());
  for(int ep = 0; ep < epoch; ++ep)
  {
    (var input, var target) = GetData();
    y = regr.op_Invocation(input);
    var loss = F.l1_loss(y, target);
    loss.backward();
    opt.step();
    Console.WriteLine(loss);
  }
}

```

</td>
<td>

```C#
using Console from System;
using torch from System.AI;
using nn from System.AI.torch;
using functional from System.AI.torch.nn as F;
using optim from System.AI.torch;

public sealed class LinearRegression : nn.Module
{

public:

  weight;

  bias;

  constructor()
  {
    this.weight = new nn.Parameter(torch.randn());
    this.bias = new nn.Parameter(torch.randn());
  }

  forward(x)
  {
    return x * this.weight + this.bias;
  }

}

get_data(batch_size)
{
  return (torch.randn(batch_size), torch.randn(batch_size));
}

main()
{
  var regr = new LinearRegression();
  var opt = new optim.SGD(regr.parameters());
  for(int ep = 0; ep < epoch; ++ep)
  {
    (var input, var target) = GetData();
    y = regr(input);
    var loss = F.l1_loss(y, target);
    loss.backward();
    opt.step();
    Console.WriteLine(loss);
  }
}
```

</table>

# Compatibility

B# is compatible with given operating systems and .NET implementations:

| OS                                        | .NET                                                    |
|:-----------------------------------------:|:-------------------------------------------------------:|
| MS Windows XP and higer                   | Mono 2.0, .NET Framework 4.0 and higer, .NET Core, .NET |
| Apple macOS 12.0 and higer                | Mono 2.0, .NET Core, .NET                               |
| Linux (Mint, Ubuntu)                      | Mono 2.0, .NET Core, .NET                               |
| Android 10 and higer                      | Mono 2.0                                                |
