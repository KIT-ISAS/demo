# Interactive HTML demonstrations

This public repository collects interactive demos, published with GitHub Pages:
<https://kit-isas.github.io/demo/>.

## Demos

- [Fib-Likelihood](https://kit-isas.github.io/demo/fib-likelihood/): coordinate-separable
  proposals and Fibonacci samples for range/bearing likelihoods.
- [Sample fusion explorer](https://kit-isas.github.io/demo/sample-fusion-explorer.html):
  browser-only interactive comparison of particle-sample fusion methods.
- [1D Gaussian](https://kit-isas.github.io/demo/gauss1d/),
  [2D Gaussian](https://kit-isas.github.io/demo/gauss2d/) and
  [Joint, marginal & conditional Gaussian](https://kit-isas.github.io/demo/conditional/):
  Gaussian sampling demos, ported from the ISAS Dash web app.
- [1D exponential family](https://kit-isas.github.io/demo/expfamily1d/): build densities
  p(x) ∝ exp(Σ θₖ Tₖ(x)) from polynomial, logarithmic, trigonometric, sigmoid and bump
  functions, with random and deterministic samples.
- [1D moments & expectations](https://kit-isas.github.io/demo/moments1d/): drag points of a
  function g(x) and follow how the density weights it into E[g(X)].

## Sources and generators

The pages here are build outputs. Edit the sources below, rebuild, and copy the result into
this repository.

| Demo | Sources and generator | Build |
| --- | --- | --- |
| `fib-likelihood/` | Repository [KIT-ISAS/COOP_FKIE_KIT](https://github.com/KIT-ISAS/COOP_FKIE_KIT), folder `Fib-Sampling/` (local: `D:\ISAS\Projects\COOP_FKIE_KIT\GitHub\Fib-Sampling`); generator `src/fib_sampling/app.py` | `uv run fib-sampling --out demo.html --cdn --no-show`, copy to `fib-likelihood/index.html` |
| `sample-fusion-explorer/` | No repository; local folder `D:\ISAS\Projects\SampleFusion\Python`; generator `experiments/fusion_explorer.py` (uses the `sample_fusion` package) | Writes `figures/fusion_explorer.html`, copy to `sample-fusion-explorer/index.html` |
| `gauss1d/`, `gauss2d/`, `conditional/`, `expfamily1d/`, `moments1d/` | Repository [KIT-ISAS/Teaching-Apps-Static](https://github.com/KIT-ISAS/Teaching-Apps-Static) (local: `D:\ISAS\Projects\WebApp\Dash-Multipage2Bokeh`); one script per demo (`<app>.py`) plus the shared `common.py`. Ported from the Dash web app [KIT-ISAS/web-app](https://github.com/KIT-ISAS/web-app) | `.venv\Scripts\python.exe <app>.py` writes `<app>.html`, copy to `<app>/index.html` |

The Fib-Likelihood page loads BokehJS from the CDN and needs an internet connection.

The sample fusion explorer is a standalone HTML build with BokehJS and its data embedded.

The Gaussian demos load BokehJS, MathJax and (conditional) Plotly.js from CDNs. `gauss2d/` fetches its Frolov
grids from `gauss2d/data/frolov/` and LCD samples from
[deterministic-samples-csv](https://github.com/KIT-ISAS/deterministic-samples-csv), so it must be
served over HTTP (not opened as a local file).
