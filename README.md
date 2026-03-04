# pyRDK
pyRDK is a Python-based secondary development framework built on top of RDK. It provides a more flexible and developer-friendly programming interface, and let users write less code.

---

# Reference
- [Flexiv RDK Home Page](https://www.flexiv.com/software/rdk) is the main reference, which contains important information including user manual and API documentation. 

- [Flexiv RDK Manual](https://www.flexiv.com/software/rdk/manual/index.html) contains the user manual.

--- 

## Compatibility

| OS                    | Platform      | Python interpreter |
|-----------------------|---------------|--------------------|
| Linux (Ubuntu 22.04+) | x86_64, aarch64	| 3.10, 3.12         |
| macOS 12+             | arm64	        | 3.10, 3.12         |

---

## Important Notice
- Robot can only run in NRT mode by pyRDK.
- In addition to the new APIs provided by pyRDK, users can still `import flexivrdk` to access and use the original interfaces, ensuring backward compatibility.

---

## Quick Start

### Install the package
```pip3 install ./pyrdk-1.8+1-py3-none-any.whl```

### Example
```python

from pyrdk.robot import Robot
from pyrdk.core.primitives.workflow import Workflow
def main():
    robot = Robot("192.168.2.10")
    robot.clear_fault()
    robot.enable(timeout=15)

    p_home = Workflow.Home(
        conditions={
            Workflow.Home.State.ReachedTarget: 1
        }
    )
    ret = robot.execute_primitive(primitive=p_home)
    return ret


if __name__ == "__main__":
    main()

```

## Documentation
Comprehensive code examples can be found in the `pyrdk/examples/` folder.