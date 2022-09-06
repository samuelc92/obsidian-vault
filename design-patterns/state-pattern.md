The State design pattern describes an open polymorphic stateful computation. The ideia behind State pattern is that clients don't interact directly with `State` object. Instead, they interact with a `Context` object that delegates operations to a `State` object, passing itself as an argument.

```csharp
public Out1 Request1(In1 in1)
{
    return State.Handle1(this, in1);
}

public Out2 Request2(In2 in2)
{
    return State.Handle2(this, in2);
}
```

Classes that derive from the abstract `State`  may then mutate `context.State`.

```csharp
public override Out2 Request2(Context context, In2 in2)
{
    if (in2 == In2.Epsilon)
	      context.State = new ConcreteStateB();

    return Out2.Eta;
}
```

Clients interact with the `Context` object and aren't aware of this internal machinery:

```csharp
var actual = ctx.Request2(in2);
```

