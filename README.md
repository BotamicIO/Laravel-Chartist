# Laravel Chartist

[![Build Status](https://img.shields.io/travis/faustbrian/Laravel-Chartist/master.svg?style=flat-square)](https://travis-ci.org/faustbrian/Laravel-Chartist)
[![PHP from Packagist](https://img.shields.io/packagist/php-v/faustbrian/laravel-chartist.svg?style=flat-square)]()
[![Latest Version](https://img.shields.io/github/release/faustbrian/Laravel-Chartist.svg?style=flat-square)](https://github.com/faustbrian/Laravel-Chartist/releases)
[![License](https://img.shields.io/packagist/l/faustbrian/Laravel-Chartist.svg?style=flat-square)](https://packagist.org/packages/faustbrian/Laravel-Chartist)

## Installation

Require this package, with [Composer](https://getcomposer.org/), in the root directory of your project.

``` bash
$ composer require faustbrian/laravel-chartist
```

## Usage

``` php
public function index()
{
    $areaChart = Chartist::name('areaChart')
                        ->type('Line')
                        ->element('areaChart')
                        ->dimension(250)
                        ->labels(['January', 'February', 'March', 'April', 'May', 'June', 'July'])
                        ->series([[
                            'label' => 'Electronics',
                            'fillColor' => 'rgba(210, 214, 222, 1)',
                            'strokeColor' => 'rgba(210, 214, 222, 1)',
                            'pointColor' => 'rgba(210, 214, 222, 1)',
                            'pointStrokeColor' => '#c1c7d1',
                            'pointHighlightFill' => '#fff',
                            'pointHighlightStroke' => 'rgba(220,220,220,1)',
                            'data' => [65, 59, 80, 81, 56, 55, 40],
                        ], [
                            'label' => 'Digital Goods',
                            'fillColor' => 'rgba(60,141,188,0.9)',
                            'strokeColor' => 'rgba(60,141,188,0.8)',
                            'pointColor' => '#3b8bba',
                            'pointStrokeColor' => 'rgba(60,141,188,1)',
                            'pointHighlightFill' => '#fff',
                            'pointHighlightStroke' => 'rgba(60,141,188,1)',
                            'data' => [28, 48, 40, 19, 86, 27, 90],
                        ]])->options([
                            'showScale' => true,
                            'scaleShowGridLines' => false,
                            'scaleGridLineColor' => 'rgba(0,0,0,.05)',
                            'scaleGridLineWidth' => 1,
                            'scaleShowHorizontalLines' => true,
                            'scaleShowVerticalLines' => true,
                            'bezierCurve' => true,
                            'bezierCurveTension' => 0.3,
                            'pointDot' => false,
                            'pointDotRadius' => 4,
                            'pointDotStrokeWidth' => 1,
                            'pointHitDetectionRadius' => 20,
                            'datasetStroke' => true,
                            'datasetStrokeWidth' => 2,
                            'datasetFill' => true,
                            'legendTemplate' => '<ul class="<%=name.toLowerCase()%>-legend"><% for (var i=0; i<datasets.length; i++){%><li><span style="background-color:<%=datasets[i].lineColor%>"></span><%if(datasets[i].label){%><%=datasets[i].label%><%}%></li><%}%></ul>',
                            'maintainAspectRatio' => false,
                            'responsive' => true,
                        ]);

    return view('home');
}
```

```html
<div class="row">
    <div class="col-md-6">
        <div class="box box-info">
            <div class="box-header">
                <h3 class="box-title">Area Chart</h3>
            </div>
            <div class="box-body">
                {!! Chartist::renderCanvas('areaChart') !!}
            </div>
        </div>
    </div>
</div>

{!! Chartist::renderScripts('areaChart') !!}
```

## Testing

``` bash
$ phpunit
```

## Security

If you discover a security vulnerability within this package, please send an e-mail to hello@brianfaust.me. All security vulnerabilities will be promptly addressed.

## Credits

- [Brian Faust](https://github.com/faustbrian)
- [All Contributors](../../contributors)

## License

[MIT](LICENSE) © [Brian Faust](https://brianfaust.me)
