# REFLECTION.md

## 1. Аль assertion хамгийн их үнэ цэнэтэй санагдсан бэ? Яагаад?

Надад хамгийн хэрэгтэй assertioн status байсан жишээ нь pm.response.to.have.status(200) ашигласнаар request амжилттай болсон эсэхийг шууд шалгаж харсан. Мөн pm.expect(json).to.have.property("username") зэрэг property assertion нь API зөв бүтэцтэй response буцааж байгаа эсэхийг шалгахад хэрэгтэй . Эдгээр assertion-ууд API өөрчлөгдөх үед алдааг хурдан илрүүлэхэд тусалсан.

## 2. Negative test-ийн жишээг тайлбарла.

Negative test дээр GET /users/999999 request ашигласан. Энэ request нь байхгүй user авах оролдлого хийж байгаа. Энэ тэст-ээр API алдаатай нөхцөлд зөв хариу өгч байгаа эсэхийг шалгах байсан. Энэ үед API 404 Not Found status болон error message буцаасан. Ингэснээр API буруу request-д зөв хариу өгч байгаа эсэхийг шалгаж чадсан.

## 3. Postman дээр ажиллаж байсан тест Newman дээр fail болсон уу? Яагаад?

Эхэндээ Postman дээр ажиллаж байсан тест Newman дээр fail болсон. Үүний шалтгаан нь environment variable зөв export хийгдээгүй бүр бичигдээгүй байсан. baseUrl хувьсагч env.dev.json файл дотор байхгүй байсан учрас Newman request-үүдийг буруу URL рүү явуулж бүгд алдаа зааж байсан.

## 4. Token эсвэл secret-ыг хэрхэн зохицуулсан бэ?

Dummy -нь өөжөө public тул аюултай байгаагүй ,Token болон environment variable-уудыг Postman environment ашиглан хадгалсан. Login request-ийн дараа pm.environment.set() ашиглаж access token болон userId хадгалсан.

## 5. API өөрчлөгдвөл collection-ийн аль хэсэг хамгийн их эвдрэх вэ? Яаж багасгах вэ?

API  structure өөрчлөгдвөл property болон business rule assertion-ууд хамгийн их эвдрэх магадлалтай. username эсвэл email field өөрчлөгдвөл тестүүд fail болно. Үүнийг багасгахын тулд flexible assertion ашиглах хэрэгтэй. Мөн environment variable болон reusable request structure ашиглах нь collection-ийн эмзэг байдлыг бууруулдаг.