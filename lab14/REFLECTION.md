# REFLECTION.md

## 1. Аль assertion хамгийн их үнэ цэнэтэй санагдсан бэ? Яагаад?

Надад хамгийн хэрэгтэй assertioн status байсан жишээ нь pm.response.to.have.status(200) ашигласнаар request амжилттай болсон эсэхийг шууд шалгаж харсан. Мөн pm.expect(json).to.have.property("username") зэрэг property assertion нь API зөв бүтэцтэй response буцааж байгаа эсэхийг шалгахад хэрэгтэй . Эдгээр assertion-ууд API өөрчлөгдөх үед алдааг хурдан илрүүлэхэд тусалсан.

## 2. Negative test-ийн жишээг тайлбарла.

Negative test дээр GET /users/999999 request ашигласан. Энэ request нь байхгүй user авах оролдлого хийж байгаа. Энэ тэст-ээр API алдаатай нөхцөлд зөв хариу өгч байгаа эсэхийг шалгах байсан. Энэ үед API 404 Not Found status болон error message буцаасан. Ингэснээр API буруу request-д зөв хариу өгч байгаа эсэхийг шалгаж чадсан.

