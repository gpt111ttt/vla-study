5. 封装常用计算函数的范例
def compute(x, y, op="add", *, scale=1.0, **options):
    """
    x, y   : 位置参数，参与计算的数
    op     : 默认参数，选择运算
    scale  : 仅限关键字参数（强制用名字传）
    options: 额外配置
    """
    ops = {
        "add": lambda a, b: a + b,
        "sub": lambda a, b: a - b,
        "mul": lambda a, b: a * b,
        "div": lambda a, b: a / b if b != 0 else float("nan"),
    }

    if op not in ops:
        raise ValueError(f"不支持的操作: {op}")

    result = ops[op](x, y) * scale
    return result, options   # 返回多个值


# 调用示例
print(compute(3, 4))                       # (7, {})
print(compute(3, 4, op="mul", scale=2))    # (24, {})
print(compute(3, 4, op="div", scale=0.5, mode="safe"))  # (0.375, {'mode': 'safe'})

一句话总结：参数负责"接收输入"（位置/关键字/可变/默认），返回值负责"输出结果"（可多个），lambda 负责"快速定义小逻辑"，三者组合就能封装出灵活、健壮的常用计算函数。


__init__ 初始化方法
class Robot:
    def __init__(self, name, dof):
        self.name = name     # 属性
        self.dof = dof

r = Robot("arm1", 6)         # 创建实例时自动调用 __init__
