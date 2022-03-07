### how to run laravel project from github?
```
git clone <my-cool-project>
composer install. or composer update
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
Go to link localhost:8000


php artisan make:model Customer -r -f -m -s -c
php artisan make:migration create_tableName
php artisan db:seed
php artisan db:seed --class = customerSeeder


php artisan --version

facker 

```
### seeder>customarSeeder.php
```
use Illuminate\Database\Seeder;
use Illuminate\Support\Facades\DB;
 
class customerSeeder extends Seeder
{
    public function run()
    {
        $path = base_path().'\customer.sql';
        //dd($path);
        $sql = file_get_contents($path);
        DB::unprepared($sql);
    }
}
```

### Models>Cutomar.php
```
use HasFactory;
protected $fillable = [
	'name',
	'contact'
];
```
