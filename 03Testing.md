# 03 Testing

Objectives

* 测试优先编程模式(testing-first programmming)
* 评价一个测试用例集(a test suite)的标准：正确性，彻底性，规模
* 通过对输入空间进行分区来设计一个合理的测试用例集
* be able to judge a test suite by measuring its code coverage
* understand and know when to use black box vs. glass box testing, unit tests vs. integration tests

## Validation(验证)

includes:

* formal reasoning(形式推理)
* code review(代码审查)
* texting(测试)

## Why software testing is hard

exhaustive testing(穷举)：耗时耗空间

haphazard testing(随意)：无代表性

random or statistical testing(随机或统计)：对物理模型有效，但对于代码来说不一定

so test cases must be chosen carefully and systematically.

## Testing-first programming

write the spec(specification:规范) and the tests before any code
order:

1. Spec: Write a specification for the function 就是对该函数的描述
2. Test
3. Implement

## Systematic testing

properties:

* Correct：用户的合法输入
* Through：要彻底的测试每种类型的数据
* Small：规模尽量小

## Choosing test cases by partitioning

divide input space into subdomains, each consisting of a set of inputs.
Then we choose one test case from each subdomain, and that's the test suite.

eg. abs
input: just one-dimension
two subdomain:
$\{a | a>=0 \} and \{a | a<0 \}$

## Include boundaries in the partition

Bugs often occur at boudaries between subdomains.

eg. 0 is the boudary between positive number and negative number.

emptiness for collection type(集合类型的空性), like empty string, empty array
把边界当做单独的一个子集

## Using multiple partitions

?

## Automated unit testing

?

## Documenting your testing strategy(记录测试策略)

```c
    describe("max", function() {
    /*
    * Testing strategy
    *
    * partition:
    *    a < b
    *    a > b
    *    a = b
    */

    it(...); // test cases here
    it(...);
    it(...);
    ...
    });
```

## Black box and glass box testing

Black box testing：在不知道函数具体实现的情况下就组织测试用例集（测试优先编程）
Glass box testing：在知道函数具体实现的情况下组织测试用例集（用来测试算法性能……）

## Coverage（覆盖）

* Statement coverage：每条语句都覆盖到
* Branch coverage：if/while 每一个分支都覆盖到
* Path coverage： 每一条实现路径都覆盖到 （几乎infeasible）

## Unit and integration testing(单元和集成测试)

integration testing tests a combination of modules,or even the entire propram.
尽量多进行单元测试，集成测试的debug非常麻烦！！！

## And so on

………………

## Summary

a good software's properties as follows:

* Safe from bugs
* Easy to understand
* Ready for change
