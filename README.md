# Generate-PDF-in-Laravel
TERMINAL :
    composer require barryvdh/laravel-dompdf

TERMINAL : 
    php artisan make:controller PDFController
WEB.PHP:
    use App\Http\Controllers\PDFController;

    Route::get('/generate-pdf', [PDFController::class, 'generatePDF']);

CONTROLLER :
    use Barryvdh\DomPDF\Facade\Pdf;

    public function generatePDF() {
        $pdf = PDF::loadView('pdf.document');
        return $pdf->download('document.pdf');
    }

