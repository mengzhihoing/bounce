# bounce

复式奖金计算方法
first代表一等，以此类推
a: 红球投注个数
b：篮球投注个数
c：命中红球个数
d：命中篮球个数


···
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
   ··· 
    
    
    胆拖奖金计算方法
    
    e: 投注胆个数
    n： 投注拖个数
    r：投注蓝球个数
    i：命中胆个数
    s：命中拖个数
    o：命中蓝个数
    
   ···
function DT(e, n, r, i, s, o) {
    var u = s <= 6 - e ? s: 6 - e,
    a = new Array;
    for (var f = 0; f <= u; f++) a[f] = i + f;
    var l = [0, 0, 0, 0, 0, 0],
    c = 0;
    if (o == 1) for (var f = 0; f <= u; f++) c = Rank(a[f], 0),
    c != -1 && (l[c] += Ccombo(n - s, 6 - e - f) * (r - 1) * Ccombo(s, f)),
    c = Rank(a[f], 1),
    l[c] += Ccombo(n - s, 6 - e - f) * Ccombo(s, f);
    if (o == 0) for (var f = 0; f <= u; f++) c = Rank(a[f], 0),
    c != -1 && (l[c] += Ccombo(n - s, 6 - e - f) * r * Ccombo(s, f));
    return l
}

function Tank(e) {
    return e == 0 ? 1 : Tank(e - 1) * e
}

function Ccombo(e, n) {
    if (n <= e) {
        var r = Tank(e - n) * Tank(n);
        return r = Tank(e) / r,
        r
    }
    return 0
}

function Rank(e, t) {
    var n = e * 1 + t * 1;
    switch (n) {
    case 7:
        return 0;
    case 6:
        return t == 1 ? 2 : 1;
    case 5:
        return 3;
    case 4:
        return 4;
    default:
        return t == 1 ? 5 : -1
    }
}

   ···
