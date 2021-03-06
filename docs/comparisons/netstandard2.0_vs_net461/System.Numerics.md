# System.Numerics

``` diff
 namespace System.Numerics {
+    [System.Runtime.InteropServices.StructLayoutAttribute(System.Runtime.InteropServices.LayoutKind.Sequential)]
+    public struct Matrix3x2 : IEquatable<Matrix3x2> {
+        public float M11;
+        public float M12;
+        public float M21;
+        public float M22;
+        public float M31;
+        public float M32;
+        public Matrix3x2(float m11, float m12, float m21, float m22, float m31, float m32);
+        public static Matrix3x2 Identity { get; }
+        public bool IsIdentity { get; }
+        public Vector2 Translation { get; set; }
+        public static Matrix3x2 Add(Matrix3x2 value1, Matrix3x2 value2);
+        public static Matrix3x2 CreateRotation(float radians);
+        public static Matrix3x2 CreateRotation(float radians, Vector2 centerPoint);
+        public static Matrix3x2 CreateScale(Vector2 scales);
+        public static Matrix3x2 CreateScale(Vector2 scales, Vector2 centerPoint);
+        public static Matrix3x2 CreateScale(float scale);
+        public static Matrix3x2 CreateScale(float scale, Vector2 centerPoint);
+        public static Matrix3x2 CreateScale(float xScale, float yScale);
+        public static Matrix3x2 CreateScale(float xScale, float yScale, Vector2 centerPoint);
+        public static Matrix3x2 CreateSkew(float radiansX, float radiansY);
+        public static Matrix3x2 CreateSkew(float radiansX, float radiansY, Vector2 centerPoint);
+        public static Matrix3x2 CreateTranslation(Vector2 position);
+        public static Matrix3x2 CreateTranslation(float xPosition, float yPosition);
+        public bool Equals(Matrix3x2 other);
+        public override bool Equals(object obj);
+        public float GetDeterminant();
+        public override int GetHashCode();
+        public static bool Invert(Matrix3x2 matrix, out Matrix3x2 result);
+        public static Matrix3x2 Lerp(Matrix3x2 matrix1, Matrix3x2 matrix2, float amount);
+        public static Matrix3x2 Multiply(Matrix3x2 value1, Matrix3x2 value2);
+        public static Matrix3x2 Multiply(Matrix3x2 value1, float value2);
+        public static Matrix3x2 Negate(Matrix3x2 value);
+        public static Matrix3x2 operator +(Matrix3x2 value1, Matrix3x2 value2);
+        public static bool operator ==(Matrix3x2 value1, Matrix3x2 value2);
+        public static bool operator !=(Matrix3x2 value1, Matrix3x2 value2);
+        public static Matrix3x2 operator *(Matrix3x2 value1, Matrix3x2 value2);
+        public static Matrix3x2 operator *(Matrix3x2 value1, float value2);
+        public static Matrix3x2 operator -(Matrix3x2 value1, Matrix3x2 value2);
+        public static Matrix3x2 operator -(Matrix3x2 value);
+        public static Matrix3x2 Subtract(Matrix3x2 value1, Matrix3x2 value2);
+        public override string ToString();
+    }
+    [System.Runtime.InteropServices.StructLayoutAttribute(System.Runtime.InteropServices.LayoutKind.Sequential)]
+    public struct Matrix4x4 : IEquatable<Matrix4x4> {
+        public float M11;
+        public float M12;
+        public float M13;
+        public float M14;
+        public float M21;
+        public float M22;
+        public float M23;
+        public float M24;
+        public float M31;
+        public float M32;
+        public float M33;
+        public float M34;
+        public float M41;
+        public float M42;
+        public float M43;
+        public float M44;
+        public Matrix4x4(Matrix3x2 value);
+        public Matrix4x4(float m11, float m12, float m13, float m14, float m21, float m22, float m23, float m24, float m31, float m32, float m33, float m34, float m41, float m42, float m43, float m44);
+        public static Matrix4x4 Identity { get; }
+        public bool IsIdentity { get; }
+        public Vector3 Translation { get; set; }
+        public static Matrix4x4 Add(Matrix4x4 value1, Matrix4x4 value2);
+        public static Matrix4x4 CreateBillboard(Vector3 objectPosition, Vector3 cameraPosition, Vector3 cameraUpVector, Vector3 cameraForwardVector);
+        public static Matrix4x4 CreateConstrainedBillboard(Vector3 objectPosition, Vector3 cameraPosition, Vector3 rotateAxis, Vector3 cameraForwardVector, Vector3 objectForwardVector);
+        public static Matrix4x4 CreateFromAxisAngle(Vector3 axis, float angle);
+        public static Matrix4x4 CreateFromQuaternion(Quaternion quaternion);
+        public static Matrix4x4 CreateFromYawPitchRoll(float yaw, float pitch, float roll);
+        public static Matrix4x4 CreateLookAt(Vector3 cameraPosition, Vector3 cameraTarget, Vector3 cameraUpVector);
+        public static Matrix4x4 CreateOrthographic(float width, float height, float zNearPlane, float zFarPlane);
+        public static Matrix4x4 CreateOrthographicOffCenter(float left, float right, float bottom, float top, float zNearPlane, float zFarPlane);
+        public static Matrix4x4 CreatePerspective(float width, float height, float nearPlaneDistance, float farPlaneDistance);
+        public static Matrix4x4 CreatePerspectiveFieldOfView(float fieldOfView, float aspectRatio, float nearPlaneDistance, float farPlaneDistance);
+        public static Matrix4x4 CreatePerspectiveOffCenter(float left, float right, float bottom, float top, float nearPlaneDistance, float farPlaneDistance);
+        public static Matrix4x4 CreateReflection(Plane value);
+        public static Matrix4x4 CreateRotationX(float radians);
+        public static Matrix4x4 CreateRotationX(float radians, Vector3 centerPoint);
+        public static Matrix4x4 CreateRotationY(float radians);
+        public static Matrix4x4 CreateRotationY(float radians, Vector3 centerPoint);
+        public static Matrix4x4 CreateRotationZ(float radians);
+        public static Matrix4x4 CreateRotationZ(float radians, Vector3 centerPoint);
+        public static Matrix4x4 CreateScale(Vector3 scales);
+        public static Matrix4x4 CreateScale(Vector3 scales, Vector3 centerPoint);
+        public static Matrix4x4 CreateScale(float scale);
+        public static Matrix4x4 CreateScale(float scale, Vector3 centerPoint);
+        public static Matrix4x4 CreateScale(float xScale, float yScale, float zScale);
+        public static Matrix4x4 CreateScale(float xScale, float yScale, float zScale, Vector3 centerPoint);
+        public static Matrix4x4 CreateShadow(Vector3 lightDirection, Plane plane);
+        public static Matrix4x4 CreateTranslation(Vector3 position);
+        public static Matrix4x4 CreateTranslation(float xPosition, float yPosition, float zPosition);
+        public static Matrix4x4 CreateWorld(Vector3 position, Vector3 forward, Vector3 up);
+        public static bool Decompose(Matrix4x4 matrix, out Vector3 scale, out Quaternion rotation, out Vector3 translation);
+        public bool Equals(Matrix4x4 other);
+        public override bool Equals(object obj);
+        public float GetDeterminant();
+        public override int GetHashCode();
+        public static bool Invert(Matrix4x4 matrix, out Matrix4x4 result);
+        public static Matrix4x4 Lerp(Matrix4x4 matrix1, Matrix4x4 matrix2, float amount);
+        public static Matrix4x4 Multiply(Matrix4x4 value1, Matrix4x4 value2);
+        public static Matrix4x4 Multiply(Matrix4x4 value1, float value2);
+        public static Matrix4x4 Negate(Matrix4x4 value);
+        public static Matrix4x4 operator +(Matrix4x4 value1, Matrix4x4 value2);
+        public static bool operator ==(Matrix4x4 value1, Matrix4x4 value2);
+        public static bool operator !=(Matrix4x4 value1, Matrix4x4 value2);
+        public static Matrix4x4 operator *(Matrix4x4 value1, Matrix4x4 value2);
+        public static Matrix4x4 operator *(Matrix4x4 value1, float value2);
+        public static Matrix4x4 operator -(Matrix4x4 value1, Matrix4x4 value2);
+        public static Matrix4x4 operator -(Matrix4x4 value);
+        public static Matrix4x4 Subtract(Matrix4x4 value1, Matrix4x4 value2);
+        public override string ToString();
+        public static Matrix4x4 Transform(Matrix4x4 value, Quaternion rotation);
+        public static Matrix4x4 Transpose(Matrix4x4 matrix);
+    }
+    [System.Runtime.InteropServices.StructLayoutAttribute(System.Runtime.InteropServices.LayoutKind.Sequential)]
+    public struct Plane : IEquatable<Plane> {
+        public Vector3 Normal;
+        public float D;
+        public Plane(Vector3 normal, float d);
+        public Plane(Vector4 value);
+        public Plane(float x, float y, float z, float d);
+        public static Plane CreateFromVertices(Vector3 point1, Vector3 point2, Vector3 point3);
+        public static float Dot(Plane plane, Vector4 value);
+        public static float DotCoordinate(Plane plane, Vector3 value);
+        public static float DotNormal(Plane plane, Vector3 value);
+        public bool Equals(Plane other);
+        public override bool Equals(object obj);
+        public override int GetHashCode();
+        public static Plane Normalize(Plane value);
+        public static bool operator ==(Plane value1, Plane value2);
+        public static bool operator !=(Plane value1, Plane value2);
+        public override string ToString();
+        public static Plane Transform(Plane plane, Matrix4x4 matrix);
+        public static Plane Transform(Plane plane, Quaternion rotation);
+    }
+    [System.Runtime.InteropServices.StructLayoutAttribute(System.Runtime.InteropServices.LayoutKind.Sequential)]
+    public struct Quaternion : IEquatable<Quaternion> {
+        public float W;
+        public float X;
+        public float Y;
+        public float Z;
+        public Quaternion(Vector3 vectorPart, float scalarPart);
+        public Quaternion(float x, float y, float z, float w);
+        public static Quaternion Identity { get; }
+        public bool IsIdentity { get; }
+        public static Quaternion Add(Quaternion value1, Quaternion value2);
+        public static Quaternion Concatenate(Quaternion value1, Quaternion value2);
+        public static Quaternion Conjugate(Quaternion value);
+        public static Quaternion CreateFromAxisAngle(Vector3 axis, float angle);
+        public static Quaternion CreateFromRotationMatrix(Matrix4x4 matrix);
+        public static Quaternion CreateFromYawPitchRoll(float yaw, float pitch, float roll);
+        public static Quaternion Divide(Quaternion value1, Quaternion value2);
+        public static float Dot(Quaternion quaternion1, Quaternion quaternion2);
+        public bool Equals(Quaternion other);
+        public override bool Equals(object obj);
+        public override int GetHashCode();
+        public static Quaternion Inverse(Quaternion value);
+        public float Length();
+        public float LengthSquared();
+        public static Quaternion Lerp(Quaternion quaternion1, Quaternion quaternion2, float amount);
+        public static Quaternion Multiply(Quaternion value1, Quaternion value2);
+        public static Quaternion Multiply(Quaternion value1, float value2);
+        public static Quaternion Negate(Quaternion value);
+        public static Quaternion Normalize(Quaternion value);
+        public static Quaternion operator +(Quaternion value1, Quaternion value2);
+        public static Quaternion operator /(Quaternion value1, Quaternion value2);
+        public static bool operator ==(Quaternion value1, Quaternion value2);
+        public static bool operator !=(Quaternion value1, Quaternion value2);
+        public static Quaternion operator *(Quaternion value1, Quaternion value2);
+        public static Quaternion operator *(Quaternion value1, float value2);
+        public static Quaternion operator -(Quaternion value1, Quaternion value2);
+        public static Quaternion operator -(Quaternion value);
+        public static Quaternion Slerp(Quaternion quaternion1, Quaternion quaternion2, float amount);
+        public static Quaternion Subtract(Quaternion value1, Quaternion value2);
+        public override string ToString();
+    }
+    [System.Runtime.InteropServices.StructLayoutAttribute(System.Runtime.InteropServices.LayoutKind.Sequential)]
+    public struct Vector2 : IEquatable<Vector2>, IFormattable {
+        public float X;
+        public float Y;
+        public Vector2(float value);
+        public Vector2(float x, float y);
+        public static Vector2 One { get; }
+        public static Vector2 UnitX { get; }
+        public static Vector2 UnitY { get; }
+        public static Vector2 Zero { get; }
+        public static Vector2 Abs(Vector2 value);
+        public static Vector2 Add(Vector2 left, Vector2 right);
+        public static Vector2 Clamp(Vector2 value1, Vector2 min, Vector2 max);
+        public void CopyTo(float[] array);
+        public void CopyTo(float[] array, int index);
+        public static float Distance(Vector2 value1, Vector2 value2);
+        public static float DistanceSquared(Vector2 value1, Vector2 value2);
+        public static Vector2 Divide(Vector2 left, Vector2 right);
+        public static Vector2 Divide(Vector2 left, float divisor);
+        public static float Dot(Vector2 value1, Vector2 value2);
+        public bool Equals(Vector2 other);
+        public override bool Equals(object obj);
+        public override int GetHashCode();
+        public float Length();
+        public float LengthSquared();
+        public static Vector2 Lerp(Vector2 value1, Vector2 value2, float amount);
+        public static Vector2 Max(Vector2 value1, Vector2 value2);
+        public static Vector2 Min(Vector2 value1, Vector2 value2);
+        public static Vector2 Multiply(Vector2 left, Vector2 right);
+        public static Vector2 Multiply(Vector2 left, float right);
+        public static Vector2 Multiply(float left, Vector2 right);
+        public static Vector2 Negate(Vector2 value);
+        public static Vector2 Normalize(Vector2 value);
+        public static Vector2 operator +(Vector2 left, Vector2 right);
+        public static Vector2 operator /(Vector2 left, Vector2 right);
+        public static Vector2 operator /(Vector2 value1, float value2);
+        public static bool operator ==(Vector2 left, Vector2 right);
+        public static bool operator !=(Vector2 left, Vector2 right);
+        public static Vector2 operator *(Vector2 left, Vector2 right);
+        public static Vector2 operator *(Vector2 left, float right);
+        public static Vector2 operator *(float left, Vector2 right);
+        public static Vector2 operator -(Vector2 left, Vector2 right);
+        public static Vector2 operator -(Vector2 value);
+        public static Vector2 Reflect(Vector2 vector, Vector2 normal);
+        public static Vector2 SquareRoot(Vector2 value);
+        public static Vector2 Subtract(Vector2 left, Vector2 right);
+        public override string ToString();
+        public string ToString(string format);
+        public string ToString(string format, IFormatProvider formatProvider);
+        public static Vector2 Transform(Vector2 position, Matrix3x2 matrix);
+        public static Vector2 Transform(Vector2 position, Matrix4x4 matrix);
+        public static Vector2 Transform(Vector2 value, Quaternion rotation);
+        public static Vector2 TransformNormal(Vector2 normal, Matrix3x2 matrix);
+        public static Vector2 TransformNormal(Vector2 normal, Matrix4x4 matrix);
+    }
+    [System.Runtime.InteropServices.StructLayoutAttribute(System.Runtime.InteropServices.LayoutKind.Sequential)]
+    public struct Vector3 : IEquatable<Vector3>, IFormattable {
+        public float X;
+        public float Y;
+        public float Z;
+        public Vector3(Vector2 value, float z);
+        public Vector3(float value);
+        public Vector3(float x, float y, float z);
+        public static Vector3 One { get; }
+        public static Vector3 UnitX { get; }
+        public static Vector3 UnitY { get; }
+        public static Vector3 UnitZ { get; }
+        public static Vector3 Zero { get; }
+        public static Vector3 Abs(Vector3 value);
+        public static Vector3 Add(Vector3 left, Vector3 right);
+        public static Vector3 Clamp(Vector3 value1, Vector3 min, Vector3 max);
+        public void CopyTo(float[] array);
+        public void CopyTo(float[] array, int index);
+        public static Vector3 Cross(Vector3 vector1, Vector3 vector2);
+        public static float Distance(Vector3 value1, Vector3 value2);
+        public static float DistanceSquared(Vector3 value1, Vector3 value2);
+        public static Vector3 Divide(Vector3 left, Vector3 right);
+        public static Vector3 Divide(Vector3 left, float divisor);
+        public static float Dot(Vector3 vector1, Vector3 vector2);
+        public bool Equals(Vector3 other);
+        public override bool Equals(object obj);
+        public override int GetHashCode();
+        public float Length();
+        public float LengthSquared();
+        public static Vector3 Lerp(Vector3 value1, Vector3 value2, float amount);
+        public static Vector3 Max(Vector3 value1, Vector3 value2);
+        public static Vector3 Min(Vector3 value1, Vector3 value2);
+        public static Vector3 Multiply(Vector3 left, Vector3 right);
+        public static Vector3 Multiply(Vector3 left, float right);
+        public static Vector3 Multiply(float left, Vector3 right);
+        public static Vector3 Negate(Vector3 value);
+        public static Vector3 Normalize(Vector3 value);
+        public static Vector3 operator +(Vector3 left, Vector3 right);
+        public static Vector3 operator /(Vector3 left, Vector3 right);
+        public static Vector3 operator /(Vector3 value1, float value2);
+        public static bool operator ==(Vector3 left, Vector3 right);
+        public static bool operator !=(Vector3 left, Vector3 right);
+        public static Vector3 operator *(Vector3 left, Vector3 right);
+        public static Vector3 operator *(Vector3 left, float right);
+        public static Vector3 operator *(float left, Vector3 right);
+        public static Vector3 operator -(Vector3 left, Vector3 right);
+        public static Vector3 operator -(Vector3 value);
+        public static Vector3 Reflect(Vector3 vector, Vector3 normal);
+        public static Vector3 SquareRoot(Vector3 value);
+        public static Vector3 Subtract(Vector3 left, Vector3 right);
+        public override string ToString();
+        public string ToString(string format);
+        public string ToString(string format, IFormatProvider formatProvider);
+        public static Vector3 Transform(Vector3 position, Matrix4x4 matrix);
+        public static Vector3 Transform(Vector3 value, Quaternion rotation);
+        public static Vector3 TransformNormal(Vector3 normal, Matrix4x4 matrix);
+    }
+    [System.Runtime.InteropServices.StructLayoutAttribute(System.Runtime.InteropServices.LayoutKind.Sequential)]
+    public struct Vector4 : IEquatable<Vector4>, IFormattable {
+        public float W;
+        public float X;
+        public float Y;
+        public float Z;
+        public Vector4(Vector2 value, float z, float w);
+        public Vector4(Vector3 value, float w);
+        public Vector4(float value);
+        public Vector4(float x, float y, float z, float w);
+        public static Vector4 One { get; }
+        public static Vector4 UnitW { get; }
+        public static Vector4 UnitX { get; }
+        public static Vector4 UnitY { get; }
+        public static Vector4 UnitZ { get; }
+        public static Vector4 Zero { get; }
+        public static Vector4 Abs(Vector4 value);
+        public static Vector4 Add(Vector4 left, Vector4 right);
+        public static Vector4 Clamp(Vector4 value1, Vector4 min, Vector4 max);
+        public void CopyTo(float[] array);
+        public void CopyTo(float[] array, int index);
+        public static float Distance(Vector4 value1, Vector4 value2);
+        public static float DistanceSquared(Vector4 value1, Vector4 value2);
+        public static Vector4 Divide(Vector4 left, Vector4 right);
+        public static Vector4 Divide(Vector4 left, float divisor);
+        public static float Dot(Vector4 vector1, Vector4 vector2);
+        public bool Equals(Vector4 other);
+        public override bool Equals(object obj);
+        public override int GetHashCode();
+        public float Length();
+        public float LengthSquared();
+        public static Vector4 Lerp(Vector4 value1, Vector4 value2, float amount);
+        public static Vector4 Max(Vector4 value1, Vector4 value2);
+        public static Vector4 Min(Vector4 value1, Vector4 value2);
+        public static Vector4 Multiply(Vector4 left, Vector4 right);
+        public static Vector4 Multiply(Vector4 left, float right);
+        public static Vector4 Multiply(float left, Vector4 right);
+        public static Vector4 Negate(Vector4 value);
+        public static Vector4 Normalize(Vector4 vector);
+        public static Vector4 operator +(Vector4 left, Vector4 right);
+        public static Vector4 operator /(Vector4 left, Vector4 right);
+        public static Vector4 operator /(Vector4 value1, float value2);
+        public static bool operator ==(Vector4 left, Vector4 right);
+        public static bool operator !=(Vector4 left, Vector4 right);
+        public static Vector4 operator *(Vector4 left, Vector4 right);
+        public static Vector4 operator *(Vector4 left, float right);
+        public static Vector4 operator *(float left, Vector4 right);
+        public static Vector4 operator -(Vector4 left, Vector4 right);
+        public static Vector4 operator -(Vector4 value);
+        public static Vector4 SquareRoot(Vector4 value);
+        public static Vector4 Subtract(Vector4 left, Vector4 right);
+        public override string ToString();
+        public string ToString(string format);
+        public string ToString(string format, IFormatProvider formatProvider);
+        public static Vector4 Transform(Vector2 position, Matrix4x4 matrix);
+        public static Vector4 Transform(Vector2 value, Quaternion rotation);
+        public static Vector4 Transform(Vector3 position, Matrix4x4 matrix);
+        public static Vector4 Transform(Vector3 value, Quaternion rotation);
+        public static Vector4 Transform(Vector4 vector, Matrix4x4 matrix);
+        public static Vector4 Transform(Vector4 value, Quaternion rotation);
+    }
 }
```

