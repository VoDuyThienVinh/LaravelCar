Neu dung git clone ve
docker-compose up
docker-compose exec app composer install
docker-compose exec app php artisan key:generate

docker-compose -f docker-compose.yml --env-file .env exec app composer install
docker-compose -f docker-compose.yml --env-file .env exec app php artisan key:generate
docker-compose -f docker-compose.yml --env-file .env exec app php artisan migrate

GRANT ALL ON laravel.* TO 'user'@'%' IDENTIFIED BY 'pass';
FLUSH PRIVILEGES;


docker-compose -f docker-compose.yml --env-file .env exec app npm --version
docker-compose -f docker-compose.yml --env-file .env exec app npm install
docker-compose -f docker-compose.yml --env-file .env exec app npm install eslint --save-dev
Copy file eslint.trc vao
docker-compose -f docker-compose.yml --env-file .env exec app npm init @eslint/config    Cai nay chi can khoi tao

JS CHECK CONVENTION
them "eslint": "eslint 'resources/js/**/*.{js,vue}'" vao package json
chay lenh npm run eslint de kiem tra
npm run eslint:fix de fix loi
npm run eslint:watch

PHP CHECK CONVENTION
composer global require "squizlabs/php_codesniffer=*"
composer global config bin-dir --absolute
export PATH="/root/.composer/vendor/bin:$PATH"
source ~/.bashrc

PHP CHECK CONVENTION Framgia
cd ~/.composer/vendor/squizlabs/php_codesniffer/src/Standards
git clone https://github.com/wataridori/framgia-php-codesniffer FramgiaPHPCS
phpcs --config-set installed_paths ~/.composer/vendor/squizlabs/php_codesniffer/src/Standards/FramgiaPHPCS

phpcs --standard=Framgia app
phpcs --standard=<bộ_quy_tắc> <đường_dẫn_file_hoặc_folder> [--report=<định_dạnh_output>]
phpcbf --standard=Framgia app/User.php


phpcs -i
Sau do them file eslint nay vao

Viet script test environment
Test lenh config
docker-compose build để rebuild image

He thong unix thi file nen la LF !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
Git se tu chuyen LF sang CRLF
git config core.autocrlf false (de tat tinh nang)


checkout - Clone code từ github - đây là lệnh mặc định của CircleCI.
run: [lệnh] - Các lệnh cần thực hiện.
restore_cache - Khôi phục lại folder chứa cái package (vendor/) dựa trên file composer.lock
save_cache - Lưu lại folder vendor nesu file composer.lock bị thay đổi hay do bạn xóa hoặc thêm package mới.
Việc cache lại folder vendor giúp tăng tốc cho bản build của bạn cho những lần chạy sau vì thay vì phải install lại các package thì đầu thì ta có thể tái sử dụng lại folder vendor của bản build trước đó nếu file composer.lock không bị thay đổi.

module.exports = {
	'env': {
		'browser': true,
		'commonjs': true,
		'es2021': true
	},
	'extends': 'eslint:recommended',
	'parserOptions': {
		'ecmaVersion': 'latest'
	},
	'rules': {
		'indent': [
			'error',
			'tab'
		],
		'linebreak-style': [
			'error',
			'windows'
		],
		'quotes': [
			'error',
			'single'
		],
		'semi': [
			'error',
			'always'
		]
	}
};