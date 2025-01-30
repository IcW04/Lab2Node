Esto son los errores que se identificaron:

	1.	Registra un usuario:
// error
curl -X POST -H "Content-Type: application/json" -d '{"username": "admin", "password": "123456"}' https://localhost/auth/register --insecure
// correcto
curl -X POST -H "Content-Type: application/json" -d "{\"username\": \"admin\", \"password\": \"123456\"}" "https://localhost/auth/register" --insecure


	2.	Inicia sesión y obtén un token:
// error
curl -X POST -H "Content-Type: application/json" -d '{"username": "admin", "password": "123456"}' https://localhost/auth/login --insecure

// correcto
curl -X POST -H "Content-Type: application/json" -d "{\"username\": \"admin\", \"password\": \"123456\"}" https://localhost/auth/login --insecure


	3.	Accede a una ruta protegida:

curl -H "Authorization: Bearer TU_TOKEN" https://localhost/private/dashboard --insecure
// Poner el token
curl -H "Authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY3OWJlMDFiNjZhMzQ2YmMxNGEwN2FjZSIsImlhdCI6MTczODI2OTI4MCwiZXhwIjoxNzM4MjcyODgwfQ.epCrtOmIUJBpQjc0z0c27tqO_iMjq2p6qETTAjIMpcg" https://localhost/private/dashboard --insecure
