# GESTOR-DE-TAREAS
RESTAURANTE   "LA CARRETA"
const clearLoginForm = () => {
    setLoginForm({ username: \'\', password: \'\', showPassword: false });
  };

  const renderLogin = () => (
    <div className="login-container">
      <div className="restaurant-hero">
        <div className="hero-content">
          <h1>🍽️ Restaurante LA CARRETA</h1>
          <p>Sistema de Gestión Profesional</p>
        </div>
      </div>
      
      <div className="login-form-container">
        <form onSubmit={handlELogin} className="login-form">
          <h2>Iniciar Sesión</h2>
          
          <div className="form-group">
            <label>Usuario</label>
            <input
              type="text"
              value={loginForm.username}
              onChange={(e) => setLoginForm({...loginForm, username: e.target.value})}
              onFocus={clearLoginForm}
              placeholder="Ingresa tu usuario"
              required
            />
          </div>
          
          <div className="form-group password-group">
            <label>Contraseña</label>
            <div className="password-input">
              <input
                type={loginForm.showPassword ? "text" : "password"}
                value={loginForm.password}
                onChange={(e) => setLoginForm({...loginForm, password: e.target.value})}
                onFocus={() => {if (!loginForm.username) clearLoginForm();}}
                placeholder="Ingresa tu contraseña"
                required
              />
              <button
                type="button"
                className="password-toggle"
                onClick={() => setLoginForm({...loginForm, showPassword: !loginForm.showPassword})}
              >
                {loginForm.showPassword ? <EyeOff size={20} /> : <Eye size={20} />}
              </button>
            </div>
          </div>
          
          <div className="form-buttons">
            <button type="submit" className="btn-primary" disabled={loading}>
              {loading ? \'Iniciando...\' : \'Iniciar Sesión\'}
            </button>
            
            <button type="button" onClick={clearLoginForm} className="btn-secondary">
              Limpiar
            </button>
          </div>
          
          <div className="auth-links">
            <button type="button" onClick={() => setCurrentView(\'forgot-password\')} className="link-button">
              ¿Olvidaste tu contraseña?
            </button>
            <button type="button" onClick={() => setCurrentView(\'register\')} className="link-button">
              Crear nuevo usuario
            </button>
          </div>
        </form>
      </div>
    </div>
  );
