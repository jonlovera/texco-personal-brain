The full Docker recipe (from a clean docker compose up)

For future reference, after the containers are up you need three steps:

# 1. Rebuild the schema + seed reference data (roles, permissions, etc.)
docker compose exec laravel.test php artisan migrate:fresh --seed

# 2. Create a user (seeders create roles but NOT accounts)
docker compose exec laravel.test php artisan tinker --execute="
  \$u = App\Models\User::firstOrCreate(['email'=>'jlovera@texco.net.au'],['name'=>'J Lovera']);
  \$u->assignRole('Super Admin');
"

# 3. Log in — visit this URL in your browser (local-only route):
#    http://localhost/dev/login/jlovera@texco.net.au

After step 3 you'll land on the dashboard as a Super Admin. Frontend assets are already built (public/build exists); if you change Vue/JS files, run docker compose exec laravel.test npm run build or ... npm run dev.
