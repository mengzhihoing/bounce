# bounce

复式奖金计算方法
first代表一等，以此类推
a: 红球投注个数
b：篮球投注个数
c：命中红球个数
d：命中篮球个数

```

    function calFirst(a, b, c, d) {
        var A = new Number(a);
        var B = new Number(b);
        var C = new Number(c);
        var D = new Number(d);
        var value = D * comp(6, C) * comp(0, A - C);
        return value;
    }

    function calSecond(a, b, c, d) {
        var A = new Number(a);
        var B = new Number(b);
        var C = new Number(c);
        var D = new Number(d);
        var value = (B - D) * comp(6, C) * comp(0, A - C);
        return value;
    }

    function calThird(a, b, c, d) {
        var A = new Number(a);
        var B = new Number(b);
        var C = new Number(c);
        var D = new Number(d);
        var value = D * comp(5, C) * comp(1, A - C);
        return value;
    }

    function calFourth(a, b, c, d) {
        var A = new Number(a);
        var B = new Number(b);
        var C = new Number(c);
        var D = new Number(d);
        var value = D * comp(4, C) * comp(2, A - C) + (B - D) * comp(5, C) * comp(1, A - C);
        return value;
    }

    function calFiveth(a, b, c, d) {
        var A = new Number(a);
        var B = new Number(b);
        var C = new Number(c);
        var D = new Number(d);
        var value = D * comp(3, C) * comp(3, A - C) + (B - D) * comp(4, C) * comp(2, A - C);
        return value;
    }

    function calSixth(a, b, c, d) {
        var A = new Number(a);
        var B = new Number(b);
        var C = new Number(c);
        var D = new Number(d);
        var value = D * comp(2, C) * comp(4, A - C) + D * comp(1, C) * comp(5, A - C) + D * comp(0, C) * comp(6, A - C);
        return value;
    }

    function comp(head, foot) {
        var A = new Number(head);
        var B = new Number(foot);
        var C = 1;
        for (var i = B - A + 1; i <= B; i++) {
            C = C * i;
        }
        for (var i = 2; i <= A; i++) {
            C = C / i;
        }
        return C;
    }
    
    ```
