EA Agent Loader
============

[![Build Status](https://img.shields.io/travis/electronicarts/ea-agent-loader.svg)](https://travis-ci.org/electronicarts/ea-agent-loader)

EA Agent Loader is a collection of utilities for [java agent](https://docs.oracle.com/javase/8/docs/api/java/lang/instrument/package-summary.html) developers.
It allows programmers to write and test their java agents using dynamic agent loading (without using the -javaavent jvm parameter).
It was developed by [BioWare](http://www.bioware.com), a division of [Electronic Arts](http://www.ea.com) and was originally part of the [Orbit Project](https://github.com/electronicarts/orbit).

License
=======
EA Agent Loader  is licensed under the [BSD 3-Clause License](./LICENSE).

Example
=======
```java
public class HelloAgentWorld
{
    public static class HelloAgent
    {
        public static void agentmain(String agentArgs, Instrumentation inst)
        {
            System.out.println(agentArgs);
            System.out.println("Hi from the agent!");
            System.out.println("I've got instrumentation!: " + inst);
        }
    }

    public static void main(String[] args)
    {
        AgentLoader.loadAgentClass(HelloAgent.class.getName(), "Hello!");
    }
}
```
