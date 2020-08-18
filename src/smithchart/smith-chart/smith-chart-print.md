# Print and Export

## Print

The rendered smithchart can be printed directly from the browser by calling the public method print. ID of the smithchart's div element must be passed as argument to that method.

```csharp

<SfSmithchart Series="SmithChartSeriesData"></SfSmithchart>

@code {
    public List<object> SmithChartSeriesData { get; set; } = new List<object> {
        new {
            points = new List<object>{
                new { resistance= 10, reactance= 25 }, new { resistance= 8, reactance= 6 },
                new { resistance= 6, reactance= 4.5 }, new { resistance= 4.5, reactance= 2 },
                new { resistance= 3.5, reactance= 1.6 }, new { resistance= 2.5, reactance= 1.3 },
                new { resistance= 2, reactance= 1.2 }, new { resistance= 1.5, reactance= 1 },
                new { resistance= 1, reactance= 0.8 }, new { resistance= 0.5, reactance= 0.4 },
                new { resistance= 0.3, reactance= 0.2 }, new { resistance= 0.001, reactance= 0.15 },
            }
        }
    };
}
```

document.getElementById('print').onclick = () => {
    smithchart.print();
};

## Export

The rendered smithchart can be exported to JPEG , PNG, SVG or PDF format by using export method in smithchart. Input parameters for this method are Export Type for format and fileName of result.

```csharp

<SfSmithchart Series="SmithChartSeriesData"></SfSmithchart>

@code {
    public List<object> SmithChartSeriesData { get; set; } = new List<object> {
        new {
            points = new List<object>{
                new { resistance= 10, reactance= 25 }, new { resistance= 8, reactance= 6 },
                new { resistance= 6, reactance= 4.5 }, new { resistance= 4.5, reactance= 2 },
                new { resistance= 3.5, reactance= 1.6 }, new { resistance= 2.5, reactance= 1.3 },
                new { resistance= 2, reactance= 1.2 }, new { resistance= 1.5, reactance= 1 },
                new { resistance= 1, reactance= 0.8 }, new { resistance= 0.5, reactance= 0.4 },
                new { resistance= 0.3, reactance= 0.2 }, new { resistance= 0.001, reactance= 0.15 },
            }
        }
    };
}
```

document.getElementById('print').onclick = () => {
    smithchart.export('PNG', 'result');
};
