# Introductory Guide to Building an Artificial Brain

*Version 0.5*

**Start building:**  [The core of an artificial brain](#01-the-core-of-an-artificial-brain) · [Building your first artificial brain](#15-building-your-first-artificial-brain) · [Useful operating points](#08-useful-operating-points) · [Observing and extending your brain](#16-observing-and-extending-your-brain)



** GET YOUR DEV KIT (Shipping now): ** [Prima-Lux Dev Kit: Up to 10,000 Synthetic Neurons](https://artificialbrains.ai)



## Contents

- [00 Introductory note to artificial brains](#00-introductory-note-to-artificial-brains)
- [01 The core of an artificial brain](#01-the-core-of-an-artificial-brain)
- [02 How this is different from current AI](#02-how-this-is-different-from-current-ai)
- [03 Rhythms](#03-rhythms)
- [04 Choosing how an OPU operates with TNorm](#04-choosing-how-an-opu-operates-with-tnorm)
- [05 Inputs and outputs](#05-inputs-and-outputs)
- [06 How to connect two OPUs](#06-how-to-connect-two-opus)
- [07 From OPUs to a primitive](#07-from-opus-to-a-primitive)
- [08 Useful operating points](#08-useful-operating-points)
- [09 Boolean logic and fuzzy logic](#09-boolean-logic-and-fuzzy-logic)
- [10 Decision nuclei disagreement and veto](#10-decision-nuclei-disagreement-and-veto)
- [11 Sensory pathways](#11-sensory-pathways)
- [12 Association memory and learning](#12-association-memory-and-learning)
- [13 Motor primitives and embodied behavior](#13-motor-primitives-and-embodied-behavior)
- [14 The ACK primitive and timing between body and brain](#14-the-ack-primitive-and-timing-between-body-and-brain)
- [15 Building your first artificial brain](#15-building-your-first-artificial-brain)
- [16 Observing and extending your brain](#16-observing-and-extending-your-brain)
- [17 Share your projects](#17-share-your-projects)
- [License](#license)

## 00 Introductory note to artificial brains

We created Artificial Brains to explore a form of intelligence closer to the way biology works, especially for machines that live and act in the physical world. We have found a distinctive approach to biomimetic intelligence using a new way of computing that relies on neural dynamics. We believe this new form of computation is bigger than us, and that's why we're opening this up so more people can start building biomimetic intelligence. If hundreds, and hopefully thousands, of people begin building artificial brains, the community can discover possibilities we could never explore alone. We will keep advancing the research, creating more capable neural engines and creating new approaches, but we also want others to build on this foundation.

This booklet explains how to begin: choose populations, connect them into useful primitives, and bring those primitives together in a brain. The examples show how sensations, memory, comparisons, and actions can become part of the same neural activity.

## 01 The core of an artificial brain

An artificial brain is a network of interacting populations of synthetic neurons that exchange information through neural dynamics. Each population has its own evolving activity. When we connect populations, we create new dynamics that can process sensations, preserve and recall memory, compare states, support decisions, and control actions, all in a biomimetic way.

A group of our synthetic neurons that share similar characteristics is called an **Oscillatory Processing Unit (OPU)**. An OPU has a rhythm and a TNorm. Together, they help determine how it operates when connected to other OPUs. The resulting pattern of activity is its neural state, also called an **Oscillatory Occupancy State (OOS)**.

An OPU on its own does not give us a meaningful computation. When two OPUs interact, they form the smallest computational unit in an artificial brain: a direct relationship between a **source OPU** and a **target OPU**.

```text
SOURCE OPU [rhythm, TNorm] → TARGET OPU [rhythm, TNorm]
```

The operation that emerges depends on the two OPUs, their TNorm values, incoming activity, and the other populations connected to them. The same rhythm labels do not guarantee the same result in every brain. Identical architectures, however, can produce a reproducible neural operation.

When we combine OPUs into a circuit that produces a useful computation or behavior, we call it a **primitive**. A primitive might compare two signals, recognize a changing condition, retain context, or move part of a robot. Combining primitives lets us build increasingly capable artificial brains.

## 02 How this is different from current AI

Most AI today learns by training large models on large collections of examples. During training, the model's connections are adjusted so it becomes better at producing an expected answer. A common method for doing this is **backpropagation**.

Artificial Brains takes a different approach. We connect populations of synthetic neurons so their neural activity can interact, change, and form new states. A brain processes information as it arrives. What it experiences can influence the way its populations respond later.

**The computation happens through neural dynamics. It does not require backpropagation or training a model on a large dataset.** We do not design a primitive by manually adjusting connection strengths (weights) until it produces the answer we want. We design how the populations interact.

Memory can work differently, too. Instead of saving a copy of an experience and looking it up later, a circuit can retain information through its evolving neural activity. This means the past experience is transformed by the present moment and the present moment is influenced by the past experience. When a related input arrives, that activity can become useful again if we know how to connect the OPUs.

Not every collection of OPUs automatically learns. We build a circuit, let it experience something, and observe whether its later responses change. That is how we investigate memory and learning in an artificial brain.

## 03 Rhythms

Each OPU has a **rhythm**. Like the rhythms found in biological brains, different rhythms give neural populations different ways to respond to information over time. The simplest way to start is to think of them from fastest to slowest.

| Rhythm | Relative speed | What it is useful for |
| --- | --- | --- |
| High-Gamma | Fastest | Relay. It does not generate an OOS when interacting as a target. |
| Gamma | Faster | Filtering noise before another OPU processes a signal. It does not generate an OOS when interacting as a target. |
| Beta | Fast | Producing action states, driving motor activity, and responding quickly when conditions change. |
| Alpha | Moderate | Transforming, separating, and reorganizing neural states; connecting different parts of a memory pathway. |
| Theta | Slow | Processing sensations, comparing states, association of inputs, preparing actions, and passing information to other OPUs. |
| Delta | Slowest | Combining present activity with earlier context, maintaining evolving states, and supporting memory pathways. |

A rhythm is not a predefined behavior. A theta OPU does not automatically recognize an object, and a delta OPU does not automatically remember one. **The useful behavior emerges when we connect the right populations and give them the right operating points.**

High-gamma is an ordinary designable OPU. We can place it throughout a brain, including internal pathways and feedback, and give it a TNorm like the other rhythms. Using it to relay an external input is one useful pattern.

## 04 Choosing how an OPU operates with TNorm

**TNorm** is a number between **0 and 10** that helps us choose the kind of neural activity an OPU will produce when it connects to another OPU.

The SDK accepts up to two decimal places for every rhythm.

| TNorm | What it means |
| --- | --- |
| 0 | The point where collective neural activity begins to form. It does not mean the OPU is switched off. |
| 2–3 | A lower operating region. Often useful for selective activity, comparisons, and some logic operations. |
| 5 | A middle operating region used in many of our tested relationships. |
| 7–8 | A higher operating region in which more activity can join together and change the resulting state. |
| 10 | The upper boundary, where activity patterns can begin to merge and saturate. It is not a better or stronger version of every operation. |

Both OPUs in a relationship can have their own TNorm. A **Theta T5 → Beta T2** connection can produce a different neural state from **Theta T5 → Beta T3**.

A small difference can matter. When a useful circuit specifies **TNorm 2.01**, use 2.01, not 2.

**TNorm chooses the operating point. It does not tell us whether a connection is excitatory or inhibitory.** That is a separate choice, explained next.

TNorm is a different concept from weights in AI. It selects the operating point and changes the neural dynamics; it is not simply a measure of the strength of a connection. It also does not specify an inhibition percentage, a fuzzy truth value, or a motor gain.

For high-gamma, `brain.opu("RELAY", "high-gamma", 10)` makes the operating point explicit. When its TNorm is omitted, high-gamma uses the default reference at 10. The other rhythms require a TNorm.

## 05 Inputs and outputs

An artificial brain receives information through **input populations** and expresses its results through **output populations**. The language of a brain, and of our artificial brains, is spikes.

An input might represent pixels from a camera, sound features from a microphone, distances, touch, or the position of a robot joint. One input population can carry an ordered vector of values. For example, one retinal input can carry an entire small image; you do not need a separate graph path for every pixel. Keep the order and meaning of those values consistent between the sensor and the brain.

An input is a population of neurons that brings information into the brain. Its useful size depends on the rhythm of the OPU receiving it. If the input causes the receiving OPU to exceed its useful capacity, its activity will saturate and it will no longer produce useful computation.

Use these recommended maximum input sizes to avoid saturating the receiving pathway:

| Rhythm | Maximum neurons per input |
| --- | --- |
| Gamma | 6 |
| Beta | 37 |
| Alpha | 44 |
| Theta | 156 |
| Delta | 498 |

When connecting to high-gamma directly from an input, use the recommendation for the rhythmic OPU after it. For input → high-gamma → theta, the recommended maximum is 156. If an input branches toward several receiving rhythms, choose its size with all of those pathways in mind.

The SDK accepts 1–498 neurons per external input. This accepted range and the maximum above answer different questions: a size can be accepted by the SDK and still saturate a particular receiving pathway. The width of an input is not the size of the OPU receiving it.

A good practice is to create one sensory motor path per meaningful input. For example, if you have three different proximity sensors, treat them as three paths before connecting them.

Name external inputs for meaningful signals entering the brain, such as RETINA, TOUCH, OBJECT\_X, or JOINT\_POSITION. We form comparisons, conditions, and fuzzy thresholds inside the brain. Those internal results can feed another primitive without becoming extra inputs calculated by the controller.

Outputs are simpler. An output is a signal the brain sends to something outside the brain. Give each output a clear name, such as LEFT, RIGHT, FOUND, FLEX, or EXTEND. An output can represent a neural decision, a sensory state worth observing, or an action sent to a body. Take into account that outputs behave like bistable neurons, and a circuit needs a way to turn an output off when it should no longer remain active (e.g. via self-inhibition).

In the SDK, `brain.output("ACTION")` creates an output with one bistable neuron by default. Use `brain.output("ACTION", n)` when the design calls for a different number. The output needs a clearing pathway appropriate to the lifetime of the signal it carries.

**Inputs bring spikes into the brain. OPUs do the computation. Outputs tell us via spikes what the brain produced. The spikes from an output are what you will use to move an actuator, a synthetic muscle, a light, or anything you want to create.**

Our SDK has encoders and decoders out of the box, so you can use them to send your signals and read them out as spikes. See the examples on our GitHub.

### Keeping the neuron budget in mind

Prima-Lux has a total capacity of 10,000 synthetic neurons. An OPU represents a population, so counting boxes on the Canvas or counting connections does not give us the total neuron count. Relays, helpers, and feedback populations also use neurons. Let the build calculate the allocation for the design.

## 06 How to connect two OPUs

Start by asking: **What do I want the target to do with the activity coming from the source?** Pass it on? Compare it? Bring different information together? Stop an unwanted response?

1. **Choose the source.** This is the OPU that already carries useful activity.
2. **Choose the target.** Give it the rhythm and TNorm you want to try.
3. **Choose the connection.** The source can excite the target or inhibit it.
4. **Connect the OPUs.** The target receives the source's activity and produces its own changing neural state.
5. **Observe the result.** Look at the target's activity and at the outputs of the larger circuit.

| Connection | Meaning | What it can be used for |
| --- | --- | --- |
| Excitatory: A → B | Activity in A helps recruit activity in B. | Relaying, combining signals, forming associations, or supporting an action. |
| Inhibitory: A —\| B | Activity in A opposes or suppresses activity in B. | Cancellation, filtering competing states, stopping an action, or creating a veto. |

An inhibitory connection is not automatically a complete veto. For example, **contradiction** can reduce support for an action without stopping it completely, while a **veto** is intended to suppress it.

Connections between OPUs are excitatory by default. This means activity in the source helps activate the target. When we want one OPU to oppose or suppress another, we need to specify the connection should be inhibitory.

The relationship is directed: **Theta → Beta** is not the same as **Beta → Theta**. When a target connects to another OPU, it becomes the source of the next relationship. You can also connect a later OPU back to an earlier one. That is called **feedback**.

The immediate source is the population directly connected to a target. If a signal has already passed through several OPUs, the last OPU is the source of the next relationship. Its activity already contains the effects of that earlier pathway.

When several OPUs excite the same gamma, beta, alpha, theta, or delta OPU, use a common rhythm for the sources directly feeding it. If the original sources use different rhythms, pass each through its own intermediate OPU in the chosen rhythm and TNorm, then connect those intermediates to a separate receiving operator. These additional OPUs count toward the neuron budget.

For example, an alpha source and a beta source can each feed their own Theta T2 relay. Those two relays can then feed a separate Theta T2 comparison population. A relay and an operator remain different populations even when their rhythm and TNorm match. For an arithmetic comparison, both the positive and the negative operands need that compatible representation.

This common-rhythm rule does not restrict a high-gamma receiver. An inhibitory veto or feedback return also has a different job from an arithmetic operand, so it does not require the same relay treatment.

### Describing the connections in the SDK

The SDK uses `brain.connect("A", "B")` for a connection from A to B. It is excitatory by default. Add `"inh"` for inhibition. Use `role="feedback"` when a later population returns activity to an earlier OPU. An output can also feed back through an OPU, as we will see in the ACK primitive.

### How much each signal contributes to an operation

Some operations need more than the direction of a connection. We also need to describe how much each signal contributes to the calculation. We call a signal that contributes to an operation an **operand**. One unit means one equal contribution at the receiving operation; it does not mean one neuron or a raw connection weight.

To compare A with B, we can give A one excitatory unit and B one inhibitory unit. Their matched contributions can cancel, leaving activity that represents the difference. In the SDK, we describe both connections with `role="operand"` and `units=1`:

```python
# A, B, and RESULT are existing populations.
brain.connect("A", "RESULT", role="operand", units=1)
brain.connect("B", "RESULT", "inh", role="operand", units=1)
```

Mark every term in an arithmetic operation, including the positive ones. The unit value is positive; the inhibitory connection supplies the opposing contribution. Values such as 0.5, 1, and 2 describe different relationships in the recipes, so preserve the value specified for each connection.

### Choosing inhibitory strength

An inhibitory connection opposes a receiving population. It can reduce competing activity, help compare signals, or help an action switch off. **The amount of inhibition is chosen on the connection, not in TNorm.**

- **0%:** no inhibitory connection; simply don't connect A to B.
- **10–50%:** lighter opposition relative to the calculated reference.
- **90–100%:** stronger opposition relative to that reference.
- The default inhibition is 100%, unless it’s specified in the design.

**Important:** 90% intensity does *not* mean exactly 90% of the receiving neurons stop firing. It means 90% of the connection's calculated reference inhibitory strength. The result depends on the activity of the whole circuit. Experiment with the number to find the response your primitive needs.

In the SDK, `strength=0.9` means 90% of the calculated reference inhibitory strength, and the default `strength=1` means 100%. The value must be finite and at least 0.1. There is no upper cap: 1.25, 2.5, and 4 are also allowed when a design calls for stronger inhibition. For zero inhibition, omit the connection.

We use inhibition for different jobs. In an arithmetic operation, an inhibitory operand cancels a specified contribution. Keep its recipe units and the default strength of 1. A veto or reset is intended to suppress a state, so choose its strength according to the suppression and recovery that pathway needs. Increasing an arithmetic subtraction term changes the operation.

Self-inhibition lets a neural state help turn itself off using feedback. The active OPU excites a second OPU, which inhibits the first one. This is useful for preventing an action from remaining active indefinitely. A high-gamma relay can first carry a sensor event into this circuit. High-gamma can also take part in a clearing feedback path, as it does in the ACK example.

## 07 From OPUs to a primitive

A **primitive** is a small circuit that produces something useful. It can contain two OPUs, several OPUs, multiple inputs, inhibitory connections, and feedback.

To create one, decide what it should do. Perhaps it should compare two locations, detect an approaching object, keep track of an earlier signal, or move a joint in one direction.

Give the primitive an input, connect the OPUs that carry out the operation, and identify its result. Add feedback when the result must change as new information arrives.

A primitive can be reused. A sensory primitive can feed a comparison primitive. That comparison can feed a decision circuit, which can activate a motor primitive.

```text
OPUs → primitive → combined primitives → artificial brain.
```

An input to a primitive can be an existing internal OPU. Reusing that result preserves the neural work already done by the preceding circuit; it does not require another external input population.

When we reuse a primitive, we preserve its full source-to-target relationships. Adding or removing gamma, high-gamma, or a relay changes the conditions reaching the next stage. The directed connections define the calculation; the order in which we declare populations or arrange their boxes does not.

## 08 Useful operating points

These are starting relationships and circuits from our neural dynamics experiments. The rhythm and TNorm values matter because changing them can change what the circuit does.

### Relaying and transforming information

| Relationship | Useful for |
| --- | --- |
| Theta T2 → Theta T2 | Passing a changing neural state to another theta population. Used in tested sensorimotor circuits. |
| Beta T5 → Beta T5 | Relaying an already active state into another fast population. |
| Theta T5 → Beta T2 | Recruiting a moderate amount of activity in a receiving population. |
| Theta T5 → Beta T3 | Forming a more compact state that can support an action. |
| Theta T5 → Alpha T5 | Carrying a state into an alpha pathway for readout or further processing. |
| Theta T3 → Theta T2.01 → Beta T5 | A useful chain for sensory processing (sensory input) and for preparing motor output (minimum unit of a motor cortex). |

### Logic comparisons and decisions

| Operation or circuit | Useful starting point |
| --- | --- |
| OR | An excitatory shared target at Beta T5 or Theta T5. A and B each contribute one operand unit. |
| NOT | Theta T5 receiving one unit of active reference and one opposing unit of A. |
| AND | Delta T2 receiving one unit each of A and B, opposed by one unit of a local Delta T2 OR helper. |
| XOR | Alpha T5 receiving two units of OR, opposed by one unit each of A and B. |
| NOR | Beta T5 receiving one unit of active reference, opposed by one unit of local OR. |
| Greater than / less than | Two Theta T2 comparison populations, one receiving A opposed by B and the other B opposed by A. |
| Two conditions must agree | A local Delta T2 coincidence rule receiving 0.5 units from each of two compatible conditions. |
| Agreement and contradiction | Two kinds of evidence entering the same decision: one supports the action, the other opposes it. |
| Motor veto | Beta T5 —\| opposing Theta T2.01 to suppress an antagonist action pathway. |
| Motor reset | Beta T5 → reset Beta T3. The reset inhibits its own Theta T2.01 and also clears the output when a fresh decision is needed. |

### Associations memory and movement

| Circuit | Useful for | Example |
| --- | --- | --- |
| 2 or more streams of Beta T5 → Delta T2 | Association primitive. Combines two pieces of information experienced together into a new neural state. | A robot sees a cup while hearing the word “cup,” creating an association between them. |
| Delta T2 → Alpha T5 → Delta T2 | Memory primitive. Keeps information from an earlier experience available in the brain. | The robot retains the association after the cup is no longer in view. |
| Delta T2 → Alpha T5 → Delta T2 → Alpha T5 → Association primitive \[Delta T2\] | Memory recall primitive. Brings information from an earlier experience back to the association primitive, where it can combine with new information. | The robot sees the cup again and recalls its association with the word “cup.” |
| Delta T2 → Theta T3 → Theta T2.01 → Beta T5 | Decision primitive. A Delta result from another primitive can feed the motor preparation chain to help the brain decide what to do. | The robot recognizes the cup and decides to reach for it. |
| Theta T3 → Theta T2.01 → Beta T5 → Output | Motor primitive. Turns neural activity into movement, allowing the brain to control a body. | The robot moves its arm toward the cup, adjusting its movement as it gets closer. |

The tables show where to start, not an entire ready-made brain. For logic, the receiving rhythm and TNorm name a useful target. The original signals can come from different rhythms; use separate relays when their immediate representations need to be brought into the same operation. [Chapter 09](#09-boolean-logic-and-fuzzy-logic) explains the local helper populations and operand contributions.

A circuit that works on its own may behave differently when connected to more OPUs. Start with these relationships, observe the results, then build outward.

## 09 Boolean logic and fuzzy logic

Boolean logic lets neural circuits represent things like **A OR B**, **A AND B**, and **A but NOT B**. The output comes from the activity of connected OPUs, not from a software rule that chooses the answer for them.

For OR, A and B both excite the same receiving OPU. For NOT, an input opposes an active reference. For AND, the receiving OPU combines A and B while a local OR contribution is inhibitory. For XOR, the circuit retains the case where only one input is active. The operating points are listed in [Chapter 08](#08-useful-operating-points); the contributions below explain how to connect them.

A and B here are populations that already carry neural conditions. Their receiving target gives the operation its rhythm and TNorm. Earlier sensory populations can have other rhythms, provided their immediate contributions are brought into the representation the operation needs.

| Operation | Excitatory operand units | Inhibitory operand units | Receiving target |
| --- | --- | --- | --- |
| OR | A 1<br>B 1 | None | Beta T5 or Theta T5 |
| AND | A 1<br>B 1 | Local OR 1 | Delta T2 |
| XOR | OR 2 | A 1<br>B 1 | Alpha T5 |
| NOT | Active REF 1 | A 1 | Theta T5 |
| NOR | Active REF 1 | Local OR 1 | Beta T5 |

XOR uses two units of OR and one opposing unit from each original operand. That factor of two is part of the operation. For all of these arithmetic connections, keep the default inhibitory strength and express the required contribution through the operand units.

### Building the local helper for AND

AND uses two distinct Delta T2 populations. The first combines A and B as a local OR helper. The second receives A and B and is opposed by that helper. This local helper is part of the Delta construction; a standalone OR at Beta T5 or Theta T5 has a different role.

In this example, A\_CAN and B\_CAN are already represented as Delta T2 operands:

```python
brain.opu("OR_LOCAL", "delta", 2)
brain.connect("A_CAN", "OR_LOCAL", role="operand", units=1)
brain.connect("B_CAN", "OR_LOCAL", role="operand", units=1)

brain.opu("AND_RESULT", "delta", 2)
brain.connect("A_CAN", "AND_RESULT", role="operand", units=1)
brain.connect("B_CAN", "AND_RESULT", role="operand", units=1)
brain.connect("OR_LOCAL", "AND_RESULT", "inh",
              role="operand", units=1)
```

The local OR contributes one unit of cancellation. Treating it as a stronger veto changes the relationship. Keep the helper and the receiving AND as separate populations, even though both are Delta T2.

Read the receiving OPU to follow its current logical state. If we expose the result through a named output, that output is bistable and may remain active after the condition changes. Give it an intentional clearing path when the result should end.

### Giving absence a positive reference

When A is inactive, it sends no positive signal saying “NOT A.” We need something active for A to oppose. A REF population supplies that reference. For NOT at Theta T5, REF contributes one excitatory unit and A contributes one inhibitory unit. Their immediate representations must be compatible.

NOR uses the same idea, with a local OR as the opposing contribution. We also need a reference or default-state mechanism when a decision should produce a positive response to the absence of evidence. Silence by itself cannot supply new positive action evidence.

### Comparing changing values

We can also compare two changing values. One pathway represents the difference when **A is greater than B**; another represents the opposite difference. These are called **opposing rails**. They are useful for movement, error correction, and decisions.

We create two separate Theta T2 comparison populations. In the first, A excites and B inhibits. In the second, B excites and A inhibits. With A\_CAN and B\_CAN already represented as Theta T2 operands, the connections are:

```python
brain.opu("A_GREATER", "theta", 2)
brain.opu("B_GREATER", "theta", 2)
brain.connect("A_CAN", "A_GREATER", role="operand", units=1)
brain.connect("B_CAN", "A_GREATER", "inh",
              role="operand", units=1)
brain.connect("B_CAN", "B_GREATER", role="operand", units=1)
brain.connect("A_CAN", "B_GREATER", "inh",
              role="operand", units=1)
```

Matched contributions cancel. The remaining activity represents the direction and amount of unmatched evidence. We can use this to compare a desired position with the actual position of a body part. Give the brain those observations so the neural comparison produces the difference.

Silence in both directions can mean the values match, but it can also mean that neither side carries active evidence. If we need a positive equality signal, we must provide an intentional reference or default-state mechanism.

For addition, the operand units enter the receiving operation through excitatory connections. When later computation needs an exact ordered quantity, keep its separate unit positions available. Compressing the result into one population readout can lose the upper part of its range.

### Keeping the meaning of a comparison over time

Addition and subtraction can retain activity from the preceding operation. When we want a fresh, independent comparison, we can let the earlier response settle or use a local clearing stage that prepares the next operation. When the earlier context is useful, we retain it deliberately. Resetting the whole brain after every observation would discard that context.

A single silent timestep does not tell us the state of a rhythmic population. Follow its firing pattern over its rhythm, from the source to the comparison target and then to the population using the result.

### Representing a gradual value

Fuzzy logic is useful when a condition is gradual instead of simply true or false. An object might be near, very near, or almost touching. We represent this with an ordered bank of neural conditions. Each position corresponds to a threshold, and the complete activity pattern represents the gradual value.

Imagine eight positions arranged from the lowest threshold to the highest. The first position means the condition has reached one eighth, the second two eighths, and so on. At one quarter, the first two positions are active. At three quarters, the first six are active. Eight is an example resolution; it is not a required width.

| Described level | Ordered bank |
| --- | --- |
| 0 | `00000000` |
| 0.25 | `11000000` |
| 0.50 | `11110000` |
| 0.75 | `11111100` |
| 1 | `11111111` |

A 1 in this table means an active Boolean condition expressed through neural activity. It does not require one particular neuron to fire at every timestep. Each position keeps a consistent meaning, and we preserve that order throughout the circuit.

TNorm 5 does not mean a fuzzy value of 0.5. A half-unit connection does not mean “half true.” The ordered pattern carries the value; an arbitrary fraction of firing neurons or a single average firing rate does not replace it.

### Combining fuzzy values

For fuzzy OR, matching positions perform OR at Beta T5 or Theta T5. For fuzzy NOT, we reverse the position order and then apply NOT at Theta T5, using an active reference. For fuzzy AND, matching positions use the local Delta T2 AND construction. This lets later OPUs work with the whole value rather than a single yes-or-no answer.

With cumulative banks, fuzzy OR represents the maximum and fuzzy AND the minimum. Combining 11000000 with 11111100 gives OR 11111100 and AND 11000000. Reversing and then complementing 11000000 gives NOT 11111100.

At each fuzzy AND position, A and B are Delta T2 operands. Their OR helper and their separate AND result are also Delta T2. Each operand contributes one excitatory unit to the AND result, and the local OR contributes one inhibitory unit. Use this local helper rather than substituting a standalone Beta OR followed by a relay.

For fuzzy NOT, the first result position receives the last source position, the second receives the next-to-last, and so on. More generally, result position j is opposed by source position m + 1 − j, together with its active reference. This reversal keeps the complement cumulative.

### Keeping a fuzzy value available to the next primitive

These banks are made from internal conditions already formed by sensory and comparison primitives. Names such as A\_1 through A\_8 identify those internal populations. They do not ask the controller to create eight new external inputs. The public `connect()` API connects whole named populations; it does not select an individual input neuron by index.

We keep each resulting position separate so the next fuzzy operation can use the complete value. If the next operation needs a common-rhythm relay, relay each position separately. Its immediate source is the generated neural population, whose state already reflects the preceding operation.

Observe the whole bank over complete cycles of the receiving rhythm, especially for a Delta AND bank. Look at which positions are active and whether their order remains meaningful. A window shorter than that rhythm can give an incomplete picture.

Sometimes we only need several conditions to support or oppose an action. The shallow decision nucleus in the next chapter serves that purpose. Its activity can grow as more evidence agrees with an action, but that activity is not itself an ordered fuzzy value. Keep the reusable fuzzy AND and the local half-unit coincidence rule as distinct constructions.

## 10 Decision nuclei disagreement and veto

A robot often has several possible actions. The same movement may help in one direction but make another part of the task worse. A **shallow decision nucleus** is a small neural circuit that receives the reasons for and against each candidate action.

A decision can use three kinds of relationships:

- **Agreement:** a condition supports an action because its expected effect helps the current goal.
- **Contradiction:** a condition opposes an action because its expected effect works against the goal.
- **Veto:** a particular condition suppresses an action that should not happen.

Agreement and contradiction can act together. An action does not have to be rejected because it has one disadvantage; several neural signals can support or oppose it at once. A veto is different: it is meant to stop activity in a specified pathway.

### Bringing two conditions together

A shallow decision nucleus brings local evidence directly to candidate actions. When a rule depends on two conditions being present together, one useful construction is a Delta T2 coincidence population. Two compatible internal conditions each contribute 0.5 units to it:

```python
# A and B already carry the two internal conditions.
brain.opu("RULE", "delta", 2)
brain.connect("A", "RULE", role="operand", units=0.5)
brain.connect("B", "RULE", role="operand", units=0.5)
```

Their coexistence supports the intended rule state. The half-units describe this construction; they do not assign a fuzzy truth degree or halve a condition's importance. Preserve the upstream operating points and follow the rule's neural pattern as either condition changes.

For a rule such as “A supports this action unless B is present,” A can excite the rule and B can inhibit it directly. The local opposition can serve the rule without adding a separate NOT population and an AND tree. Choose that inhibition for the suppression needed in the receiving state; it serves a different purpose from a one-unit arithmetic subtraction.

A rule built only from absent conditions still needs a positive reference, a default state, or a complement mechanism. Silence can mean no correction, or a command already being held, but it cannot supply a new positive reason to act.

### Relating evidence to the body

For each candidate action, we compare its expected effect on the body with the current neural comparison and body context. Matching effects provide agreement. Opposing effects provide contradiction to that same candidate. Use signed operand units to describe those contributions; contradiction does not automatically act as a veto.

Suppose ELBOW\_EXTEND would move the gripper toward X+, Y+, and Z+ in its current posture. If the required direction is X−, Y−, and Z+, the Z condition supports that movement while X and Y oppose it. All three contributions can act at the same time.

Build the agreeing and opposing rules from the same body context. More simultaneous support can recruit more activity in the candidate, but that activity is not a normalized fuzzy number. Keep exact comparisons and reusable fuzzy values upstream when another operation needs their explicit meaning.

We can express deliberate importance through meaningful repeated rule structure or explicit operand units. Duplicating external sensor inputs merely to create more evidence changes what the inputs mean. The controller supplies observations and translates neural outputs; the brain compares the evidence and selects the action. Python should not subtract candidate baselines, normalize candidate activity, or choose the largest candidate.

For movements that oppose each other, such as **FLEX** and **EXTEND** at the same joint, we can connect inhibitory pathways between the opponents. Different joints do not have to compete when their actions can work together.

**The decision is a neural output.** It is produced by the activity of the decision circuit, not by an external rule that chooses a winner.

## 11 Sensory pathways

Every artificial brain needs information to work with. A camera, microphone, touch sensor, distance sensor, or robot joint can supply inputs.

One retinal input population can carry many pixels in one ordered signal. A microphone input can carry sound features. A robot joint can provide its actual position. Different kinds of inputs can be given their own named populations.

One useful sensory chain is:

```text
INPUT → THETA T3 → THETA T2.01 → BETA T5 → NEXT OPU
```

The first OPUs organize the incoming activity so the next circuit can use it. We can then create a visual state, compare it with another state, associate it with a sound, or send it toward a motor decision.

For comparisons, use real information from the body and environment. If the brain must reach an object, it should compare the object's observed position with the **actual gripper position**. It should not assume that the gripper is always at the center of the camera.

A high-gamma relay can carry an input into this sensory chain. Match the input width to the following rhythm and preserve the meaning of its ordered values. This lets later primitives use the same observation consistently.

In a simulator, physical observations can include the gripper's coordinates calculated from the body's current joint positions. These coordinates describe where the body is. The neural comparison still produces the directional difference, and the decision circuit chooses the movement. An inverse-kinematics solution or a controller-computed error would supply part of that answer instead of its observations.

## 12 Association memory and learning

An **associative primitive** is a group of connected OPUs where two or more pieces of information can become part of the same neural state.

Think of an object with both a shape and a color. One sensory path carries the shape and another carries the color. When their activity meets in an associative population, it can form a shared state that reflects the **combined experience**. We can bring in more information, such as sound or touch, using the same principle. Biological brains operate with this principle: association.

**Memory adds another step.** The associative state enters a recurrent pathway that allows earlier activity to influence what happens later. One useful memory relationship we have tested is:

```text
ASSOCIATIVE PRIMITIVE [DELTA T2] → DELTA T2 → ALPHA T5 → DELTA T2 → ALPHA T5 → ASSOCIATIVE PRIMITIVE [DELTA T2]
```

The last Alpha OPU connects back to the same association primitive that received the original information. When the brain encounters something familiar, the memory can influence the new information arriving there. This allows the brain to recall a previous experience and use it to make a decision.

Our team has observed evidence of memory through neural dynamics in a specific circuit. It does not mean every new association or every memory task will work automatically.

A useful way to build memory is to separate three jobs: **combine** sensations in an associative primitive, **maintain and transform** the combined state through a memory circuit, and **return** that state to the associative primitive so a partial cue can influence a later decision.

This is also how we investigate learning from experience. We give a brain something to experience and then test whether its future response changes, whether earlier associations remain available, and whether a new association can change an old response. **There is no backpropagation step.**

### Giving each part of the memory pathway its own population

The return pathway contains distinct populations even where a rhythm appears more than once. Here, VISION\_BETA and SOUND\_BETA are existing Beta T5 sensory results. Their shared association enters the memory pathway, and the last alpha population returns to the same ASSOC population:

```python
brain.opu("ASSOC", "delta", 2)
brain.opu("MEM_D1", "delta", 2)
brain.opu("MEM_A1", "alpha", 5)
brain.opu("MEM_D2", "delta", 2)
brain.opu("MEM_A2", "alpha", 5)
brain.connect("VISION_BETA", "ASSOC")
brain.connect("SOUND_BETA", "ASSOC")
brain.connect("ASSOC", "MEM_D1")
brain.connect("MEM_D1", "MEM_A1")
brain.connect("MEM_A1", "MEM_D2")
brain.connect("MEM_D2", "MEM_A2")
brain.connect("MEM_A2", "ASSOC", role="feedback")
```

Keep the incoming sensory sources and the memory return distinguishable in the design. The return brings earlier activity back into contact with a new cue.

### Following what the brain retains

Persistent firing alone does not tell us which experience has been remembered. Follow the pattern when a cue appears, disappears, and returns. Then see how a partial cue changes the association and the response that follows it. Two states can have similar total firing while different neurons participate or their activity develops differently over time.

Stop saves the neural state. Reset dynamics discards accumulated neural changes and memory. It does not reset the robot's physical posture or the surrounding world; the application remains responsible for that external context.

## 13 Motor primitives and embodied behavior

A brain that controls a body needs to know what it wants to do, what the body is currently doing, and how each movement changes the situation.

For each opposing movement, create its own primitive. A joint can have one **FLEX** primitive and one **EXTEND** primitive. They can inhibit each other, but other joints can act at the same time. FLEX and EXTEND can use the same primitive design, with opposite outputs.

A useful starting motor chain is:

```text
THETA T3 → THETA T2.01 → BETA T5 → MOTOR OUTPUT
```

A comparison circuit can receive an object's current location and the position of the gripper. It creates neural signals for the directions in which the target and the gripper differ. Those signals enter the decision nucleus. The decision nucleus can then support or oppose each joint's movement according to what it would do to the body.

The movement changes the body. New sensory information arrives. The brain makes another decision. **That continuous feedback loop is what lets a motor primitive adapt its activity while it acts.**

Decision rules feed this motor pathway through their source-to-target relationships. If a rule already produces a useful Delta result, it can feed the motor preparation chain. We do not need to add another serial Delta action population merely because the rules use Delta.

### Letting opposing movements inhibit each other

For FLEX and EXTEND at the same joint, motor Beta T5 can inhibit the opposing Theta T2.01. When the opposing command must also stop, give that pathway responsibility for clearing the opposing output. Shoulder and elbow movements can remain active together; add competition where the body has an antagonist relationship.

### Clearing the motor state and its output

A motor pathway contains two states we need to think about separately: the activity inside its OPUs and the signal held by its output. Outputs are bistable, so an output can remain active after the neural condition that first activated it has changed. Turning down the internal motor state does not necessarily turn off that output.

| What the command should do | Neural arrangement |
| --- | --- |
| Hold until replaced or cleared | Keep the output latched and give an opposing or explicit clearing path responsibility for stopping it. |
| Reconsider the evidence after an action | Add a motor reset branch that inhibits its own Theta T2.01 and clears its own output. |

If we want the brain to reconsider the movement after each action, motor Beta T5 excites a reset Beta T3 population. That reset population inhibits its own Theta T2.01 and also clears the output. Continuing evidence can then support another action.

```python
# T2, MOTOR, and ACTION already form a motor pathway.
brain.opu("RESET", "beta", 3)
brain.connect("MOTOR", "RESET")
brain.connect("RESET", "T2", "inh", role="feedback")
brain.connect("RESET", "ACTION", "inh")
```

The omitted strengths use the calculated reference. Choose the suppression required on each inhibitory connection. Suppressing a rhythmic OPU and clearing a bistable output are distinct receiving jobs; an OPU's suppression behavior does not automatically describe its output.

Follow the sequence from local rule, to motor Theta T2.01, to motor Beta T5, to output, and then to body movement. If an action continues after its evidence has changed, inspect the output latch and its clearing path as well as the decision OPU.

### Translating outputs into physical commands

The controller translates neural outputs into physical commands and applies the body's speed, force, and joint limits. An active output may appear in several successive frames. Decide whether the driver treats those frames as incremental commands or as one held state, and use the matching decoder. That choice determines how the same neural output is expressed by the body.

## 14 The ACK primitive and timing between body and brain

A robot's body and brain don't necessarily operate at the same speed. Cameras, sensors, motors, and neural populations may all have different timing.

The ACK (acknowledgement) primitive helps synchronize them. It produces a neural signal that lets the controller know a new observation has reached the brain, so the controller can distinguish the response to that observation from activity produced earlier.

### How it works

1. The body sends an observation (inputs). The controller publishes the latest sensory information and activates an ACK input.
2. The brain acknowledges the input. The ACK signal passes through a high-gamma (LIF) relay, producing a fast neural response.
3. The controller receives the ACK spike. It uses that spike to establish the beginning of a new decision-reading window.
4. The controller reads the brain's outputs. It observes the subsequent neural activity and translates the relevant output spikes into actions.

The ACK tells the controller that the observation entered the acknowledgement pathway. It does not mean the entire brain has finished processing or that a decision is already available. Use it as a clock between brain and body.

### Building the ACK primitive

A simple ACK primitive uses an input population, a high-gamma relay, and a bistable output. A second high-gamma population carries the output's activity back through an inhibitory connection to clear it. Use separate populations for the incoming relay and the clearing return.

```text
ACK input → high-gamma relay → ACK output
```

```text
ACK output → high-gamma reset —| ACK output
```

For each new observation, the controller sends the associated stimulus to ACK. Allow the clearing loop to return the output before treating another active ACK as a new event. This helps keep an earlier acknowledgement from being mistaken for a new one.

High-gamma is useful because it responds quickly to incoming spikes.

The last part of the primitive provides self-inhibition so an acknowledgement can be brief. The output remains bistable; the clearing circuit gives it the lifetime this task needs.

```python
# Add this block to an existing Brain.
brain.input("ACK_IN", 1)
brain.opu("ACK_RELAY", "high-gamma", 10)
brain.output("ACK")
brain.opu("ACK_RESET", "high-gamma", 10)
brain.connect("ACK_IN", "ACK_RELAY")
brain.connect("ACK_RELAY", "ACK")
brain.connect("ACK", "ACK_RESET", role="feedback")
brain.connect("ACK_RESET", "ACK", "inh")
```

Repeated output frames containing the same held ACK are not separate acknowledgements. Sustained input can also re-excite the pathway, so follow its actual state and the clearing return when interpreting the events.

### Why it matters

The ACK primitive gives the controller a way to coordinate when sensory information enters the brain and when to observe the resulting neural activity.

This is especially useful for robots with cameras, distance sensors, and motors operating at different speeds.

The body sends information, the brain acknowledges it, and the controller uses that acknowledgement to organize the next action.

### Publishing current observations

Publish an observation when the sensor captures it. Use `session.publish_sensor_frame()` for signals captured together and `session.publish_input()` for an individual observation. These calls supply current sensory information. Do not queue future neural steps or infer a fixed neural timestep duration from the sensor polling rate.

### Receiving outputs as they become available

Register `session.on_output(callback)` before beginning sensor activity. Prima-Lux pushes each completed timestep, including unchanged output states and timesteps with no active outputs. The controller can receive those frames without requesting each one.

Use a decoder with `session.on_command(...)`, or let RobotLoop dispatch the decoded commands. RobotLoop's `tick_hz` controls how often sensors are polled; it does not set the neural rhythm or the rate at which outputs arrive. Keep output callbacks short so they can receive subsequent frames promptly.

If a connection is interrupted, the SDK attempts to resume from retained output history. It reports missing history or a changed brain run explicitly. Start a fresh session after resetting neural dynamics.

## 15 Building your first artificial brain

Start with a small, useful behavior. Decide what the brain will **sense**, what it should **produce**, and which neural operations belong between them.

1. **Name the inputs.** These are the sensory populations that bring information into the brain.
2. **Name the outputs.** These are the states or actions you want to observe.
3. **Choose your OPUs.** Give each one a role, a rhythm, and a TNorm.
4. **Connect them.** Decide which relationships should be excitatory and which should be inhibitory.
5. **Build a primitive.** Connect the smallest set of OPUs that can produce one useful result.
6. **Observe and improve it.** Test changing inputs, watch the neural outputs, and add feedback or other primitives when useful.

For AI agents, the same rule applies: **design the neural relationships, not a software shortcut to the answer.** Use the operating points in this booklet to select the first circuits, then let their activity produce the behavior.

The GitHub repository contains examples you can reproduce and build upon. This booklet gives you the concepts and connections to begin creating your own artificial brains. The [SDK README](https://github.com/artificial-brains-inc/artificial_brains/blob/main/README.md) explains application integration, and [AGENTS.md](https://github.com/artificial-brains-inc/artificial_brains/blob/main/AGENTS.md) gives coding agents the construction and integration rules to follow.

### Describing the design in Python

Use `from ab import Brain` to begin a design. Declare the inputs, OPUs, outputs, and connections, then save it as `brain.abdesign.json`. Population names begin with a letter and use letters, numbers, and underscores.

The short examples in earlier chapters show one part of a circuit and name the populations they expect to exist already. The following example is a complete small neural design. It connects one sensory input to a motor pathway and clears both the internal motor state and the output, so continuing evidence can produce another action.

```python
from ab import Brain

brain = Brain("Sensory Motor Pathway")
brain.input("SENSE", 64)
brain.opu("RELAY", "high-gamma", 10)
brain.opu("T1", "theta", 3)
brain.opu("T2", "theta", 2.01)
brain.opu("MOTOR", "beta", 5)
brain.opu("RESET", "beta", 3)
brain.output("ACTION")

brain.connect("SENSE", "RELAY")
brain.connect("RELAY", "T1")
brain.connect("T1", "T2")
brain.connect("T2", "MOTOR")
brain.connect("MOTOR", "ACTION")
brain.connect("MOTOR", "RESET")
brain.connect("RESET", "T2", "inh", role="feedback")
brain.connect("RESET", "ACTION", "inh")
brain.save("brain.abdesign.json")
```

Save the design as `brain.py`. Keep the application that reads the sensor and drives the body in `run.py`, using the same SENSE and ACTION names. The [SDK README](https://github.com/artificial-brains-inc/artificial_brains/blob/main/README.md) provides the session, decoder, and RobotLoop integration code.

### Preparing the project and building the brain

Complete device registration at `http://prima-lux.local:8080/` and obtain a developer API key. Configure the project's `.env` before building. Keep the key private:

```dotenv
AB_DEVICE_URL=http://prima-lux.local:8080/
AB_DEVICE_API_KEY=YOUR_DEVICE_API_KEY
AB_TELEMETRY=true
```

From the project directory, install the SDK, generate the design, inspect it on the Canvas, build it, and run it:

```bash
python -m pip install --upgrade artificialbrains-sdk
python brain.py
ab design --brain brain.abdesign.json
ab build brain --brain brain.abdesign.json --env .env
ab run --env .env
```

Wait for READY after building before running. Build installs the design; Run starts the installed brain and your application. A change to a local design file does not replace the installed brain until you build again. Repeat the build step when changing brains between projects, even if that design has been used before.

### Generating repeated structures

A fuzzy bank repeats the same local construction at several positions. We can describe that repetition in an ordinary Python generator. This example adds an eight-position fuzzy AND to a brain that already contains the internal Delta T2 operands A\_1 through A\_8 and B\_1 through B\_8:

```python
for j in range(1, 9):
    a = f"A_{j}"
    b = f"B_{j}"
    helper = f"OR_LOCAL_{j}"
    result = f"AND_{j}"
    brain.opu(helper, "delta", 2)
    brain.opu(result, "delta", 2)
    brain.connect(a, helper, role="operand", units=1)
    brain.connect(b, helper, role="operand", units=1)
    brain.connect(a, result, role="operand", units=1)
    brain.connect(b, result, role="operand", units=1)
    brain.connect(helper, result, "inh", role="operand", units=1)

brain.save("brain.abdesign.json")
```

Place the loop in `make_brain.py` with the code that creates the upstream operands. Run it with Python, then build the saved JSON. The Canvas Python editor and direct `--brain brain.py` import accept literal Brain declarations; they do not execute loops or helper functions.

```bash
python make_brain.py
ab build brain --brain brain.abdesign.json --env .env
ab run --env .env
```

This keeps the repeated structure in the neural design. The application continues to send meaningful observations, while the internal populations carry the thresholds and perform the fuzzy operation.

## 16 Observing and extending your brain

We learn what a circuit is doing by following its activity. Look at the source, the receiving population, the feedback, and the output together. Compare the pattern before a condition appears, while it is present, and after it changes. Give slower populations enough time to express their rhythm before interpreting silence.

### Using neuron telemetry

Set `AB_TELEMETRY=true` in the project's `.env`. When the application starts a compatible Prima-Lux session, the SDK opens the neuron telemetry window. Select an OPU to inspect its neurons and firing history. Input stimulation is displayed separately from neural firing.

Bright dots show neurons firing in the displayed timestep. Dark dots show neurons that are not firing in that timestep. The history gives one row per neuron, so we can follow which neurons join a state, how activity persists or alternates, and how the population recovers.

Freeze pauses the display while the brain and controller continue. Pan and zoom to follow a pathway. Set `AB_TELEMETRY=false`, or omit the setting, to turn the viewer off. Output streaming continues independently of that display.

### Looking at the relationship responsible for a result

For Boolean operators, observe each condition on its own and then their combination. For fuzzy operators, follow the ordered bank rather than only its total activity. For motor pathways, follow the clearing branch and output latch as well as the activity that began the movement.

If a target saturates, revisit the input width and receiving rhythm. If a comparison does not balance, check the operand units, signs, and immediate sources. If a result remains active, follow its recurrent paths and the state intended to clear it. Change the connection or operating point responsible for that role so the effect of the change remains understandable.

Use `brain.validate()` for structural and advisory warnings. Validation can help identify problems in the design, while observing neural activity tells us how the circuit behaves. Stop the session and wait for neural-state saving before powering down. Use reset dynamics when you deliberately want to discard the accumulated state.

### Making a primitive useful to someone else

Save the design alongside its application. Describe what each input means, which populations directly feed each operation, and the rhythm and TNorm choices. Record operand units, the purpose of inhibitory connections, and how long an output should remain active. Include the commands to build and run it and the activity another developer should look for.

Those details let another person or agent preserve the relationships that make the primitive useful and connect it to something new. Keep credentials out of shared projects.

## 17 Share your projects

We created Artificial Brains so people can build things we haven't imagined yet, or things we've only seen in science-fiction books and movies. Biomimetic intelligence opens the door to building robots and machines that can live lives of their own, contribute to the job market, take care of dangerous missions, expand our civilization into places we cannot yet reach, and prepare the way for our arrival. We believe many of the people who bring these possibilities to life will emerge from this community.

We want the primitives and artificial brains you create to become technologies that others need and use. You might create a primitive that other developers build upon, an artificial brain that becomes part of a commercial product, or even an entire company around your discovery.

You can choose to share your work or keep your original designs private and offer them commercially, under the applicable developer terms. We encourage you to turn your ideas into real products and businesses.

At the same time, we hope you'll share what you learn along the way. Every new experiment, discovery, and idea can help the community understand what else is possible with artificial brains.

---

## License

© 2026 Artificial Brains. Licensed under Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International (CC BY-NC-ND 4.0).

https://creativecommons.org/licenses/by-nc-nd/4.0/

All rights not expressly granted are reserved. This license does not grant patent or trademark rights.

See the [license notice, scope and full legal text](LICENSE.md).
